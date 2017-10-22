<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.rnn.LSTMStateTuple" />
<meta itemprop="property" content="c"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="h"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.contrib.rnn.LSTMStateTuple

## Class `LSTMStateTuple`



### Aliases:

* Class `tf.contrib.rnn.LSTMStateTuple`
* Class `tf.nn.rnn_cell.LSTMStateTuple`



Defined in [`tensorflow/python/ops/rnn_cell_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/rnn_cell_impl.py).

See the guide: [RNN and Cells (contrib) > Classes storing split `RNNCell` state](../../../../../api_guides/python/contrib.rnn.md#Classes_storing_split_RNNCell_state)

Tuple used by LSTM Cells for `state_size`, `zero_state`, and output state.

Stores two elements: `(c, h)`, in that order. Where `c` is the hidden state
and `h` is the output.

Only used when `state_is_tuple=True`.

## Properties

<h3 id="c"><code>c</code></h3>

Alias for field number 0

<h3 id="dtype"><code>dtype</code></h3>



<h3 id="h"><code>h</code></h3>

Alias for field number 1



## Methods

<h3 id="__new__"><code>__new__</code></h3>

``` python
__new__(
    _cls,
    c,
    h
)
```

Create new instance of LSTMStateTuple(c, h)



