<!-- DO NOT EDIT! Automatically generated file. -->
# RNN and Cells (contrib)
[TOC]

Module for constructing RNN Cells and additional RNN operations.

<h2 id="Base_interface_for_all_RNN_Cells">Base interface for all RNN Cells</h2>

*   [`tf.contrib.rnn.RNNCell`](../../api_docs/python/tf/contrib/rnn/RNNCell.md)

<h2 id="Core_RNN_Cells_for_use_with_TensorFlow_s_core_RNN_methods">Core RNN Cells for use with TensorFlow's core RNN methods</h2>

*   [`tf.contrib.rnn.BasicRNNCell`](../../api_docs/python/tf/contrib/rnn/BasicRNNCell.md)
*   [`tf.contrib.rnn.BasicLSTMCell`](../../api_docs/python/tf/contrib/rnn/BasicLSTMCell.md)
*   [`tf.contrib.rnn.GRUCell`](../../api_docs/python/tf/contrib/rnn/GRUCell.md)
*   [`tf.contrib.rnn.LSTMCell`](../../api_docs/python/tf/contrib/rnn/LSTMCell.md)
*   [`tf.contrib.rnn.LayerNormBasicLSTMCell`](../../api_docs/python/tf/contrib/rnn/LayerNormBasicLSTMCell.md)

<h2 id="Classes_storing_split_RNNCell_state">Classes storing split `RNNCell` state</h2>

*   [`tf.contrib.rnn.LSTMStateTuple`](../../api_docs/python/tf/contrib/rnn/LSTMStateTuple.md)

<h2 id="Core_RNN_Cell_wrappers_RNNCells_that_wrap_other_RNNCells_">Core RNN Cell wrappers (RNNCells that wrap other RNNCells)</h2>

*   [`tf.contrib.rnn.MultiRNNCell`](../../api_docs/python/tf/contrib/rnn/MultiRNNCell.md)
*   [`tf.contrib.rnn.LSTMBlockWrapper`](../../api_docs/python/tf/contrib/rnn/LSTMBlockWrapper.md)
*   [`tf.contrib.rnn.DropoutWrapper`](../../api_docs/python/tf/contrib/rnn/DropoutWrapper.md)
*   [`tf.contrib.rnn.EmbeddingWrapper`](../../api_docs/python/tf/contrib/rnn/EmbeddingWrapper.md)
*   [`tf.contrib.rnn.InputProjectionWrapper`](../../api_docs/python/tf/contrib/rnn/InputProjectionWrapper.md)
*   [`tf.contrib.rnn.OutputProjectionWrapper`](../../api_docs/python/tf/contrib/rnn/OutputProjectionWrapper.md)
*   [`tf.contrib.rnn.DeviceWrapper`](../../api_docs/python/tf/contrib/rnn/DeviceWrapper.md)
*   [`tf.contrib.rnn.ResidualWrapper`](../../api_docs/python/tf/contrib/rnn/ResidualWrapper.md)

### Block RNNCells
*   [`tf.contrib.rnn.LSTMBlockCell`](../../api_docs/python/tf/contrib/rnn/LSTMBlockCell.md)
*   [`tf.contrib.rnn.GRUBlockCell`](../../api_docs/python/tf/contrib/rnn/GRUBlockCell.md)

### Fused RNNCells
*   [`tf.contrib.rnn.FusedRNNCell`](../../api_docs/python/tf/contrib/rnn/FusedRNNCell.md)
*   [`tf.contrib.rnn.FusedRNNCellAdaptor`](../../api_docs/python/tf/contrib/rnn/FusedRNNCellAdaptor.md)
*   [`tf.contrib.rnn.TimeReversedFusedRNN`](../../api_docs/python/tf/contrib/rnn/TimeReversedFusedRNN.md)
*   [`tf.contrib.rnn.LSTMBlockFusedCell`](../../api_docs/python/tf/contrib/rnn/LSTMBlockFusedCell.md)

### LSTM-like cells
*   [`tf.contrib.rnn.CoupledInputForgetGateLSTMCell`](../../api_docs/python/tf/contrib/rnn/CoupledInputForgetGateLSTMCell.md)
*   [`tf.contrib.rnn.TimeFreqLSTMCell`](../../api_docs/python/tf/contrib/rnn/TimeFreqLSTMCell.md)
*   [`tf.contrib.rnn.GridLSTMCell`](../../api_docs/python/tf/contrib/rnn/GridLSTMCell.md)

### RNNCell wrappers
*   [`tf.contrib.rnn.AttentionCellWrapper`](../../api_docs/python/tf/contrib/rnn/AttentionCellWrapper.md)
*   [`tf.contrib.rnn.CompiledWrapper`](../../api_docs/python/tf/contrib/rnn/CompiledWrapper.md)


<h2 id="Recurrent_Neural_Networks">Recurrent Neural Networks</h2>

TensorFlow provides a number of methods for constructing Recurrent Neural
Networks.

*   [`tf.contrib.rnn.static_rnn`](../../api_docs/python/tf/nn/static_rnn.md)
*   [`tf.contrib.rnn.static_state_saving_rnn`](../../api_docs/python/tf/nn/static_state_saving_rnn.md)
*   [`tf.contrib.rnn.static_bidirectional_rnn`](../../api_docs/python/tf/nn/static_bidirectional_rnn.md)
*   [`tf.contrib.rnn.stack_bidirectional_dynamic_rnn`](../../api_docs/python/tf/contrib/rnn/stack_bidirectional_dynamic_rnn.md)
