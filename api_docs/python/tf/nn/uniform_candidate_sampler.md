<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.uniform_candidate_sampler" />
</div>

# tf.nn.uniform_candidate_sampler

``` python
uniform_candidate_sampler(
    true_classes,
    num_true,
    num_sampled,
    unique,
    range_max,
    seed=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/candidate_sampling_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/candidate_sampling_ops.py).

See the guide: [Neural Network > Candidate Sampling](../../../../api_guides/python/nn.md#Candidate_Sampling)

Samples a set of classes using a uniform base distribution.

This operation randomly samples a tensor of sampled classes
(`sampled_candidates`) from the range of integers `[0, range_max)`.

The elements of `sampled_candidates` are drawn without replacement
(if `unique=True`) or with replacement (if `unique=False`) from
the base distribution.

The base distribution for this operation is the uniform distribution
over the range of integers `[0, range_max)`.

In addition, this operation returns tensors `true_expected_count`
and `sampled_expected_count` representing the number of times each
of the target classes (`true_classes`) and the sampled
classes (`sampled_candidates`) is expected to occur in an average
tensor of sampled classes.  These values correspond to `Q(y|x)`
defined in [this
document](http://www.tensorflow.org/extras/candidate_sampling.pdf).
If `unique=True`, then these are post-rejection probabilities and we
compute them approximately.

#### Args:

* <b>`true_classes`</b>: A `Tensor` of type `int64` and shape `[batch_size,
    num_true]`. The target classes.
* <b>`num_true`</b>: An `int`.  The number of target classes per training example.
* <b>`num_sampled`</b>: An `int`.  The number of classes to randomly sample. The
    `sampled_candidates` return value will have shape `[num_sampled]`. If
    `unique=True`, `num_sampled` must be less than or equal to `range_max`.
* <b>`unique`</b>: A `bool`. Determines whether all sampled classes in a batch are
    unique.
* <b>`range_max`</b>: An `int`. The number of possible classes.
* <b>`seed`</b>: An `int`. An operation-specific seed. Default is 0.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

* <b>`sampled_candidates`</b>: A tensor of type `int64` and shape `[num_sampled]`.  The
    sampled classes, either with possible duplicates (`unique=False`) or all
    unique (`unique=True`). In either case, `sampled_candidates` is
    independent of the true classes.
* <b>`true_expected_count`</b>: A tensor of type `float`.  Same shape as
    `true_classes`. The expected counts under the sampling distribution
    of each of `true_classes`.
* <b>`sampled_expected_count`</b>: A tensor of type `float`. Same shape as
    `sampled_candidates`. The expected counts under the sampling distribution
    of each of `sampled_candidates`.