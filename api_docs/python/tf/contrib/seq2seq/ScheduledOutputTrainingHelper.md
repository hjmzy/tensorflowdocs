<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.seq2seq.ScheduledOutputTrainingHelper" />
<meta itemprop="property" content="batch_size"/>
<meta itemprop="property" content="sample_ids_dtype"/>
<meta itemprop="property" content="sample_ids_shape"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="initialize"/>
<meta itemprop="property" content="next_inputs"/>
<meta itemprop="property" content="sample"/>
</div>

# tf.contrib.seq2seq.ScheduledOutputTrainingHelper

## Class `ScheduledOutputTrainingHelper`

Inherits From: [`TrainingHelper`](../../../tf/contrib/seq2seq/TrainingHelper.md)



Defined in [`tensorflow/contrib/seq2seq/python/ops/helper.py`](https://www.tensorflow.org/code/tensorflow/contrib/seq2seq/python/ops/helper.py).

See the guide: [Seq2seq Library (contrib) > Dynamic Decoding](../../../../../api_guides/python/contrib.seq2seq.md#Dynamic_Decoding)

A training helper that adds scheduled sampling directly to outputs.

Returns False for sample_ids where no sampling took place; True elsewhere.

## Properties

<h3 id="batch_size"><code>batch_size</code></h3>



<h3 id="sample_ids_dtype"><code>sample_ids_dtype</code></h3>



<h3 id="sample_ids_shape"><code>sample_ids_shape</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    inputs,
    sequence_length,
    sampling_probability,
    time_major=False,
    seed=None,
    next_inputs_fn=None,
    auxiliary_inputs=None,
    name=None
)
```

Initializer.

#### Args:

* <b>`inputs`</b>: A (structure) of input tensors.
* <b>`sequence_length`</b>: An int32 vector tensor.
* <b>`sampling_probability`</b>: A 0D `float32` tensor: the probability of sampling
    from the outputs instead of reading directly from the inputs.
* <b>`time_major`</b>: Python bool.  Whether the tensors in `inputs` are time major.
    If `False` (default), they are assumed to be batch major.
* <b>`seed`</b>: The sampling seed.
* <b>`next_inputs_fn`</b>: (Optional) callable to apply to the RNN outputs to create
    the next input when sampling. If `None` (default), the RNN outputs will
    be used as the next inputs.
* <b>`auxiliary_inputs`</b>: An optional (structure of) auxiliary input tensors with
    a shape that matches `inputs` in all but (potentially) the final
    dimension. These tensors will be concatenated to the sampled output or
    the `inputs` when not sampling for use as the next input.
* <b>`name`</b>: Name scope for any created operations.


#### Raises:

* <b>`ValueError`</b>: if `sampling_probability` is not a scalar or vector.

<h3 id="initialize"><code>initialize</code></h3>

``` python
initialize(name=None)
```



<h3 id="next_inputs"><code>next_inputs</code></h3>

``` python
next_inputs(
    time,
    outputs,
    state,
    sample_ids,
    name=None
)
```



<h3 id="sample"><code>sample</code></h3>

``` python
sample(
    time,
    outputs,
    state,
    name=None
)
```





