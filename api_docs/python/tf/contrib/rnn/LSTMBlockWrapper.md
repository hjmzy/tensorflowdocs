<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.rnn.LSTMBlockWrapper" />
<meta itemprop="property" content="num_units"/>
<meta itemprop="property" content="__call__"/>
</div>

# tf.contrib.rnn.LSTMBlockWrapper

## Class `LSTMBlockWrapper`

Inherits From: [`FusedRNNCell`](../../../tf/contrib/rnn/FusedRNNCell.md)



Defined in [`tensorflow/contrib/rnn/python/ops/lstm_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/rnn/python/ops/lstm_ops.py).

See the guide: [RNN and Cells (contrib) > Core RNN Cell wrappers (RNNCells that wrap other RNNCells)](../../../../../api_guides/python/contrib.rnn.md#Core_RNN_Cell_wrappers_RNNCells_that_wrap_other_RNNCells_)

This is a helper class that provides housekeeping for LSTM cells.

This may be useful for alternative LSTM and similar type of cells.
The subclasses must implement `_call_cell` method and `num_units` property.

## Properties

<h3 id="num_units"><code>num_units</code></h3>

Number of units in this cell (output dimension).



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    inputs,
    initial_state=None,
    dtype=None,
    sequence_length=None,
    scope=None
)
```

Run this LSTM on inputs, starting from the given state.

#### Args:

* <b>`inputs`</b>: `3-D` tensor with shape `[time_len, batch_size, input_size]`
    or a list of `time_len` tensors of shape `[batch_size, input_size]`.
* <b>`initial_state`</b>: a tuple `(initial_cell_state, initial_output)` with tensors
    of shape `[batch_size, self._num_units]`. If this is not provided, the
    cell is expected to create a zero initial state of type `dtype`.
* <b>`dtype`</b>: The data type for the initial state and expected output. Required
    if `initial_state` is not provided or RNN state has a heterogeneous
    dtype.
* <b>`sequence_length`</b>: Specifies the length of each sequence in inputs. An
    `int32` or `int64` vector (tensor) size `[batch_size]`, values in `[0,
    time_len).`
    Defaults to `time_len` for each element.
* <b>`scope`</b>: `VariableScope` for the created subgraph; defaults to class name.


#### Returns:

A pair containing:

- Output: A `3-D` tensor of shape `[time_len, batch_size, output_size]`
  or a list of time_len tensors of shape `[batch_size, output_size]`,
  to match the type of the `inputs`.
- Final state: a tuple `(cell_state, output)` matching `initial_state`.


#### Raises:

* <b>`ValueError`</b>: in case of shape mismatches



