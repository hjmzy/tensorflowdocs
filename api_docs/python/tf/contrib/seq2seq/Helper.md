<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.seq2seq.Helper" />
<meta itemprop="property" content="batch_size"/>
<meta itemprop="property" content="sample_ids_dtype"/>
<meta itemprop="property" content="sample_ids_shape"/>
<meta itemprop="property" content="initialize"/>
<meta itemprop="property" content="next_inputs"/>
<meta itemprop="property" content="sample"/>
</div>

# tf.contrib.seq2seq.Helper

## Class `Helper`





Defined in [`tensorflow/contrib/seq2seq/python/ops/helper.py`](https://www.tensorflow.org/code/tensorflow/contrib/seq2seq/python/ops/helper.py).

See the guide: [Seq2seq Library (contrib) > Dynamic Decoding](../../../../../api_guides/python/contrib.seq2seq.md#Dynamic_Decoding)

Interface for implementing sampling in seq2seq decoders.

Helper instances are used by `BasicDecoder`.

## Properties

<h3 id="batch_size"><code>batch_size</code></h3>

Batch size of tensor returned by `sample`.

Returns a scalar int32 tensor.

<h3 id="sample_ids_dtype"><code>sample_ids_dtype</code></h3>

DType of tensor returned by `sample`.

Returns a DType.

<h3 id="sample_ids_shape"><code>sample_ids_shape</code></h3>

Shape of tensor returned by `sample`, excluding the batch dimension.

Returns a `TensorShape`.



## Methods

<h3 id="initialize"><code>initialize</code></h3>

``` python
initialize(name=None)
```

Returns `(initial_finished, initial_inputs)`.

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

Returns `(finished, next_inputs, next_state)`.

<h3 id="sample"><code>sample</code></h3>

``` python
sample(
    time,
    outputs,
    state,
    name=None
)
```

Returns `sample_ids`.



