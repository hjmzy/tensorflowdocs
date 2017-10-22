<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.seq2seq.BasicDecoder" />
<meta itemprop="property" content="batch_size"/>
<meta itemprop="property" content="output_dtype"/>
<meta itemprop="property" content="output_size"/>
<meta itemprop="property" content="tracks_own_finished"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="finalize"/>
<meta itemprop="property" content="initialize"/>
<meta itemprop="property" content="step"/>
</div>

# tf.contrib.seq2seq.BasicDecoder

## Class `BasicDecoder`

Inherits From: [`Decoder`](../../../tf/contrib/seq2seq/Decoder.md)



Defined in [`tensorflow/contrib/seq2seq/python/ops/basic_decoder.py`](https://www.tensorflow.org/code/tensorflow/contrib/seq2seq/python/ops/basic_decoder.py).

See the guide: [Seq2seq Library (contrib) > Dynamic Decoding](../../../../../api_guides/python/contrib.seq2seq.md#Dynamic_Decoding)

Basic sampling decoder.

## Properties

<h3 id="batch_size"><code>batch_size</code></h3>



<h3 id="output_dtype"><code>output_dtype</code></h3>



<h3 id="output_size"><code>output_size</code></h3>



<h3 id="tracks_own_finished"><code>tracks_own_finished</code></h3>

Describes whether the Decoder keeps track of finished states.

Most decoders will emit a true/false `finished` value independently
at each time step.  In this case, the `dynamic_decode` function keeps track
of which batch entries are already finished, and performs a logical OR to
insert new batches to the finished set.

Some decoders, however, shuffle batches / beams between time steps and
`dynamic_decode` will mix up the finished state across these entries because
it does not track the reshuffle across time steps.  In this case, it is
up to the decoder to declare that it will keep track of its own finished
state by setting this property to `True`.

#### Returns:

Python bool.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    cell,
    helper,
    initial_state,
    output_layer=None
)
```

Initialize BasicDecoder.

#### Args:

* <b>`cell`</b>: An `RNNCell` instance.
* <b>`helper`</b>: A `Helper` instance.
* <b>`initial_state`</b>: A (possibly nested tuple of...) tensors and TensorArrays.
    The initial state of the RNNCell.
* <b>`output_layer`</b>: (Optional) An instance of `tf.layers.Layer`, i.e.,
    `tf.layers.Dense`. Optional layer to apply to the RNN output prior
    to storing the result or sampling.


#### Raises:

* <b>`TypeError`</b>: if `cell`, `helper` or `output_layer` have an incorrect type.

<h3 id="finalize"><code>finalize</code></h3>

``` python
finalize(
    outputs,
    final_state,
    sequence_lengths
)
```



<h3 id="initialize"><code>initialize</code></h3>

``` python
initialize(name=None)
```

Initialize the decoder.

#### Args:

* <b>`name`</b>: Name scope for any created operations.


#### Returns:

`(finished, first_inputs, initial_state)`.

<h3 id="step"><code>step</code></h3>

``` python
step(
    time,
    inputs,
    state,
    name=None
)
```

Perform a decoding step.

#### Args:

* <b>`time`</b>: scalar `int32` tensor.
* <b>`inputs`</b>: A (structure of) input tensors.
* <b>`state`</b>: A (structure of) state tensors and TensorArrays.
* <b>`name`</b>: Name scope for any created operations.


#### Returns:

`(outputs, next_state, next_inputs, finished)`.



