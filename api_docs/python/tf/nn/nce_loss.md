<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.nce_loss" />
</div>

# tf.nn.nce_loss

``` python
nce_loss(
    weights,
    biases,
    labels,
    inputs,
    num_sampled,
    num_classes,
    num_true=1,
    sampled_values=None,
    remove_accidental_hits=False,
    partition_strategy='mod',
    name='nce_loss'
)
```



Defined in [`tensorflow/python/ops/nn_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/nn_impl.py).

See the guide: [Neural Network > Candidate Sampling](../../../../api_guides/python/nn.md#Candidate_Sampling)

Computes and returns the noise-contrastive estimation training loss.

See [Noise-contrastive estimation: A new estimation principle for
unnormalized statistical
models](http://www.jmlr.org/proceedings/papers/v9/gutmann10a/gutmann10a.pdf).
Also see our [Candidate Sampling Algorithms
Reference](https://www.tensorflow.org/extras/candidate_sampling.pdf)

A common use case is to use this method for training, and calculate the full
sigmoid loss for evaluation or inference. In this case, you must set
`partition_strategy="div"` for the two losses to be consistent, as in the
following example:

```python
if mode == "train":
  loss = tf.nn.nce_loss(
      weights=weights,
      biases=biases,
      labels=labels,
      inputs=inputs,
      ...,
      partition_strategy="div")
elif mode == "eval":
  logits = tf.matmul(inputs, tf.transpose(weights))
  logits = tf.nn.bias_add(logits, biases)
  labels_one_hot = tf.one_hot(labels, n_classes)
  loss = tf.nn.sigmoid_cross_entropy_with_logits(
      labels=labels_one_hot,
      logits=logits)
  loss = tf.reduce_sum(loss, axis=1)
```

Note: By default this uses a log-uniform (Zipfian) distribution for sampling,
so your labels must be sorted in order of decreasing frequency to achieve
good results.  For more details, see
[`tf.nn.log_uniform_candidate_sampler`](../../tf/nn/log_uniform_candidate_sampler.md).

Note: In the case where `num_true` > 1, we assign to each target class
the target probability 1 / `num_true` so that the target probabilities
sum to 1 per-example.

Note: It would be useful to allow a variable number of target classes per
example.  We hope to provide this functionality in a future release.
For now, if you have a variable number of target classes, you can pad them
out to a constant number by either repeating them or by padding
with an otherwise unused class.

#### Args:

* <b>`weights`</b>: A `Tensor` of shape `[num_classes, dim]`, or a list of `Tensor`
      objects whose concatenation along dimension 0 has shape
      [num_classes, dim].  The (possibly-partitioned) class embeddings.
* <b>`biases`</b>: A `Tensor` of shape `[num_classes]`.  The class biases.
* <b>`labels`</b>: A `Tensor` of type `int64` and shape `[batch_size,
      num_true]`. The target classes.
* <b>`inputs`</b>: A `Tensor` of shape `[batch_size, dim]`.  The forward
      activations of the input network.
* <b>`num_sampled`</b>: An `int`.  The number of classes to randomly sample per batch.
* <b>`num_classes`</b>: An `int`. The number of possible classes.
* <b>`num_true`</b>: An `int`.  The number of target classes per training example.
* <b>`sampled_values`</b>: a tuple of (`sampled_candidates`, `true_expected_count`,
      `sampled_expected_count`) returned by a `*_candidate_sampler` function.
      (if None, we default to `log_uniform_candidate_sampler`)
* <b>`remove_accidental_hits`</b>:  A `bool`.  Whether to remove "accidental hits"
      where a sampled class equals one of the target classes.  If set to
      `True`, this is a "Sampled Logistic" loss instead of NCE, and we are
      learning to generate log-odds instead of log probabilities.  See
      our [Candidate Sampling Algorithms Reference]
      (https://www.tensorflow.org/extras/candidate_sampling.pdf).
      Default is False.
* <b>`partition_strategy`</b>: A string specifying the partitioning strategy, relevant
      if `len(weights) > 1`. Currently `"div"` and `"mod"` are supported.
      Default is `"mod"`. See `tf.nn.embedding_lookup` for more details.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `batch_size` 1-D tensor of per-example NCE losses.