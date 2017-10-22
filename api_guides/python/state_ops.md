<!-- DO NOT EDIT! Automatically generated file. -->
# Variables

Note: Functions taking `Tensor` arguments can also take anything accepted by
[`tf.convert_to_tensor`](../../api_docs/python/tf/convert_to_tensor.md).

[TOC]

<h2 id="Variables">Variables</h2>

*   [`tf.Variable`](../../api_docs/python/tf/Variable.md)

<h2 id="Variable_helper_functions">Variable helper functions</h2>

TensorFlow provides a set of functions to help manage the set of variables
collected in the graph.

*   [`tf.global_variables`](../../api_docs/python/tf/global_variables.md)
*   [`tf.local_variables`](../../api_docs/python/tf/local_variables.md)
*   [`tf.model_variables`](../../api_docs/python/tf/model_variables.md)
*   [`tf.trainable_variables`](../../api_docs/python/tf/trainable_variables.md)
*   [`tf.moving_average_variables`](../../api_docs/python/tf/moving_average_variables.md)
*   [`tf.global_variables_initializer`](../../api_docs/python/tf/global_variables_initializer.md)
*   [`tf.local_variables_initializer`](../../api_docs/python/tf/local_variables_initializer.md)
*   [`tf.variables_initializer`](../../api_docs/python/tf/variables_initializer.md)
*   [`tf.is_variable_initialized`](../../api_docs/python/tf/is_variable_initialized.md)
*   [`tf.report_uninitialized_variables`](../../api_docs/python/tf/report_uninitialized_variables.md)
*   [`tf.assert_variables_initialized`](../../api_docs/python/tf/assert_variables_initialized.md)
*   [`tf.assign`](../../api_docs/python/tf/assign.md)
*   [`tf.assign_add`](../../api_docs/python/tf/assign_add.md)
*   [`tf.assign_sub`](../../api_docs/python/tf/assign_sub.md)

<h2 id="Saving_and_Restoring_Variables">Saving and Restoring Variables</h2>

*   [`tf.train.Saver`](../../api_docs/python/tf/train/Saver.md)
*   [`tf.train.latest_checkpoint`](../../api_docs/python/tf/train/latest_checkpoint.md)
*   [`tf.train.get_checkpoint_state`](../../api_docs/python/tf/train/get_checkpoint_state.md)
*   [`tf.train.update_checkpoint_state`](../../api_docs/python/tf/train/update_checkpoint_state.md)

<h2 id="Sharing_Variables">Sharing Variables</h2>

TensorFlow provides several classes and operations that you can use to
create variables contingent on certain conditions.

*   [`tf.get_variable`](../../api_docs/python/tf/get_variable.md)
*   [`tf.get_local_variable`](../../api_docs/python/tf/get_local_variable.md)
*   [`tf.VariableScope`](../../api_docs/python/tf/VariableScope.md)
*   [`tf.variable_scope`](../../api_docs/python/tf/variable_scope.md)
*   [`tf.variable_op_scope`](../../api_docs/python/tf/variable_op_scope.md)
*   [`tf.get_variable_scope`](../../api_docs/python/tf/get_variable_scope.md)
*   [`tf.make_template`](../../api_docs/python/tf/make_template.md)
*   [`tf.no_regularizer`](../../api_docs/python/tf/no_regularizer.md)
*   [`tf.constant_initializer`](../../api_docs/python/tf/constant_initializer.md)
*   [`tf.random_normal_initializer`](../../api_docs/python/tf/random_normal_initializer.md)
*   [`tf.truncated_normal_initializer`](../../api_docs/python/tf/truncated_normal_initializer.md)
*   [`tf.random_uniform_initializer`](../../api_docs/python/tf/random_uniform_initializer.md)
*   [`tf.uniform_unit_scaling_initializer`](../../api_docs/python/tf/uniform_unit_scaling_initializer.md)
*   [`tf.zeros_initializer`](../../api_docs/python/tf/zeros_initializer.md)
*   [`tf.ones_initializer`](../../api_docs/python/tf/ones_initializer.md)
*   [`tf.orthogonal_initializer`](../../api_docs/python/tf/orthogonal_initializer.md)

<h2 id="Variable_Partitioners_for_Sharding">Variable Partitioners for Sharding</h2>

*   [`tf.fixed_size_partitioner`](../../api_docs/python/tf/fixed_size_partitioner.md)
*   [`tf.variable_axis_size_partitioner`](../../api_docs/python/tf/variable_axis_size_partitioner.md)
*   [`tf.min_max_variable_partitioner`](../../api_docs/python/tf/min_max_variable_partitioner.md)

<h2 id="Sparse_Variable_Updates">Sparse Variable Updates</h2>

The sparse update ops modify a subset of the entries in a dense `Variable`,
either overwriting the entries or adding / subtracting a delta.  These are
useful for training embedding models and similar lookup-based networks, since
only a small subset of embedding vectors change in any given step.

Since a sparse update of a large tensor may be generated automatically during
gradient computation (as in the gradient of
[`tf.gather`](../../api_docs/python/tf/gather.md)),
an [`tf.IndexedSlices`](../../api_docs/python/tf/IndexedSlices.md) class is provided that encapsulates a set
of sparse indices and values.  `IndexedSlices` objects are detected and handled
automatically by the optimizers in most cases.

*   [`tf.scatter_update`](../../api_docs/python/tf/scatter_update.md)
*   [`tf.scatter_add`](../../api_docs/python/tf/scatter_add.md)
*   [`tf.scatter_sub`](../../api_docs/python/tf/scatter_sub.md)
*   [`tf.scatter_mul`](../../api_docs/python/tf/scatter_mul.md)
*   [`tf.scatter_div`](../../api_docs/python/tf/scatter_div.md)
*   [`tf.scatter_nd_update`](../../api_docs/python/tf/scatter_nd_update.md)
*   [`tf.scatter_nd_add`](../../api_docs/python/tf/scatter_nd_add.md)
*   [`tf.scatter_nd_sub`](../../api_docs/python/tf/scatter_nd_sub.md)
*   [`tf.sparse_mask`](../../api_docs/python/tf/sparse_mask.md)
*   [`tf.IndexedSlices`](../../api_docs/python/tf/IndexedSlices.md)

### Read-only Lookup Tables

*   [`tf.initialize_all_tables`](../../api_docs/python/tf/initialize_all_tables.md)
*   [`tf.tables_initializer`](../../api_docs/python/tf/tables_initializer.md)


<h2 id="Exporting_and_Importing_Meta_Graphs">Exporting and Importing Meta Graphs</h2>

*   [`tf.train.export_meta_graph`](../../api_docs/python/tf/train/export_meta_graph.md)
*   [`tf.train.import_meta_graph`](../../api_docs/python/tf/train/import_meta_graph.md)

# Deprecated functions (removed after 2017-03-02). Please don't use them.

*   [`tf.all_variables`](../../api_docs/python/tf/all_variables.md)
*   [`tf.initialize_all_variables`](../../api_docs/python/tf/initialize_all_variables.md)
*   [`tf.initialize_local_variables`](../../api_docs/python/tf/initialize_local_variables.md)
*   [`tf.initialize_variables`](../../api_docs/python/tf/initialize_variables.md)
