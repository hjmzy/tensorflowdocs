<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework" />
</div>

# Module: tf.contrib.framework



Defined in [`tensorflow/contrib/framework/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/__init__.py).

Framework utilities.

See the [Framework (contrib)](../../../../api_guides/python/contrib.framework.md) guide.







## Modules

[`nest`](../../tf/contrib/framework/nest.md) module: ## Functions for working with arbitrarily nested sequences of elements.

## Classes

[`class VariableDeviceChooser`](../../tf/contrib/framework/VariableDeviceChooser.md): Device chooser for variables.

## Functions

[`add_arg_scope(...)`](../../tf/contrib/framework/add_arg_scope.md): Decorates a function with args so it can be used within an arg_scope.

[`add_model_variable(...)`](../../tf/contrib/framework/add_model_variable.md): Adds a variable to the `GraphKeys.MODEL_VARIABLES` collection.

[`arg_scope(...)`](../../tf/contrib/framework/arg_scope.md): Stores the default arguments for the given set of list_ops.

[`arg_scoped_arguments(...)`](../../tf/contrib/framework/arg_scoped_arguments.md): Returns the list kwargs that arg_scope can set for a func.

[`assert_global_step(...)`](../../tf/contrib/framework/assert_global_step.md): DEPRECATED FUNCTION

[`assert_or_get_global_step(...)`](../../tf/contrib/framework/assert_or_get_global_step.md): Verifies that a global step tensor is valid or gets one if None is given.

[`assert_same_float_dtype(...)`](../../tf/assert_same_float_dtype.md): Validate and return float type based on `tensors` and `dtype`.

[`assert_scalar(...)`](../../tf/assert_scalar.md)

[`assert_scalar_int(...)`](../../tf/contrib/framework/assert_scalar_int.md): Assert `tensor` is 0-D, of type `tf.int32` or `tf.int64`.

[`assign_from_checkpoint(...)`](../../tf/contrib/framework/assign_from_checkpoint.md): Creates an operation to assign specific variables from a checkpoint.

[`assign_from_checkpoint_fn(...)`](../../tf/contrib/framework/assign_from_checkpoint_fn.md): Returns a function that assigns specific variables from a checkpoint.

[`assign_from_values(...)`](../../tf/contrib/framework/assign_from_values.md): Creates an assignment operation from a given mapping.

[`assign_from_values_fn(...)`](../../tf/contrib/framework/assign_from_values_fn.md): Returns a function that assigns specific variables from the given values.

[`convert_to_tensor_or_sparse_tensor(...)`](../../tf/convert_to_tensor_or_sparse_tensor.md): Converts value to a `SparseTensor` or `Tensor`.

[`create_global_step(...)`](../../tf/contrib/framework/create_global_step.md): Create global step tensor in graph. (deprecated)

[`current_arg_scope(...)`](../../tf/contrib/framework/current_arg_scope.md)

[`deprecated(...)`](../../tf/contrib/framework/deprecated.md): Decorator for marking functions or methods deprecated.

[`deprecated_arg_values(...)`](../../tf/contrib/framework/deprecated_arg_values.md): Decorator for marking specific function argument values as deprecated.

[`deprecated_args(...)`](../../tf/contrib/framework/deprecated_args.md): Decorator for marking specific function arguments as deprecated.

[`filter_variables(...)`](../../tf/contrib/framework/filter_variables.md): Filter a list of variables using regular expressions.

[`get_global_step(...)`](../../tf/contrib/framework/get_global_step.md): DEPRECATED FUNCTION

[`get_graph_from_inputs(...)`](../../tf/contrib/framework/get_graph_from_inputs.md): Returns the appropriate graph to use for the given inputs.

[`get_local_variables(...)`](../../tf/contrib/framework/get_local_variables.md): Gets the list of local variables, filtered by scope and/or suffix.

[`get_model_variables(...)`](../../tf/contrib/framework/get_model_variables.md): Gets the list of model variables, filtered by scope and/or suffix.

[`get_name_scope(...)`](../../tf/contrib/framework/get_name_scope.md): Returns the current name scope of the default graph.

[`get_or_create_global_step(...)`](../../tf/contrib/framework/get_or_create_global_step.md): Returns and create (if necessary) the global step tensor. (deprecated)

[`get_trainable_variables(...)`](../../tf/contrib/framework/get_trainable_variables.md): Gets the list of trainable variables, filtered by scope and/or suffix.

[`get_unique_variable(...)`](../../tf/contrib/framework/get_unique_variable.md): Gets the variable uniquely identified by that var_op_name.

[`get_variable_full_name(...)`](../../tf/contrib/framework/get_variable_full_name.md): Returns the full name of a variable.

[`get_variables(...)`](../../tf/contrib/framework/get_variables.md): Gets the list of variables, filtered by scope and/or suffix.

[`get_variables_by_name(...)`](../../tf/contrib/framework/get_variables_by_name.md): Gets the list of variables that were given that name.

[`get_variables_by_suffix(...)`](../../tf/contrib/framework/get_variables_by_suffix.md): Gets the list of variables that end with the given suffix.

[`get_variables_to_restore(...)`](../../tf/contrib/framework/get_variables_to_restore.md): Gets the list of the variables to restore.

[`has_arg_scope(...)`](../../tf/contrib/framework/has_arg_scope.md): Checks whether a func has been decorated with @add_arg_scope or not.

[`init_from_checkpoint(...)`](../../tf/contrib/framework/init_from_checkpoint.md): Using assignment map initializes current variables with loaded tensors.

[`is_tensor(...)`](../../tf/contrib/framework/is_tensor.md): Check whether `x` is of tensor type.

[`list_variables(...)`](../../tf/contrib/framework/list_variables.md): Returns list of all variables in the latest checkpoint.

[`load_and_remap_matrix_initializer(...)`](../../tf/contrib/framework/load_and_remap_matrix_initializer.md): Returns a var initializer for loading and remapping a 2-D (matrix) tensor.

[`load_checkpoint(...)`](../../tf/contrib/framework/load_checkpoint.md): Returns CheckpointReader for latest checkpoint.

[`load_embedding_initializer(...)`](../../tf/contrib/framework/load_embedding_initializer.md): Returns a variable initializer for loading pre-trained embeddings.

[`load_linear_multiclass_bias_initializer(...)`](../../tf/contrib/framework/load_linear_multiclass_bias_initializer.md): Loads pre-trained multi-class biases for linear models from checkpoint.

[`load_variable(...)`](../../tf/contrib/framework/load_variable.md): Returns a Tensor with the contents of the given variable in the checkpoint.

[`load_variable_slot_initializer(...)`](../../tf/contrib/framework/load_variable_slot_initializer.md): Loads pre-trained multi-class slots for linear models from checkpoint.

[`local_variable(...)`](../../tf/contrib/framework/local_variable.md): Create variable and add it to `GraphKeys.LOCAL_VARIABLES` collection.

[`model_variable(...)`](../../tf/contrib/framework/model_variable.md): Gets an existing model variable with these parameters or creates a new one.

[`prepend_name_scope(...)`](../../tf/contrib/framework/prepend_name_scope.md): Prepends name scope to a name.

[`reduce_sum_n(...)`](../../tf/contrib/framework/reduce_sum_n.md): Reduce tensors to a scalar sum.

[`remove_squeezable_dimensions(...)`](../../tf/contrib/framework/remove_squeezable_dimensions.md): Squeeze last dim if ranks of `predictions` and `labels` differ by 1. (deprecated)

[`strip_name_scope(...)`](../../tf/contrib/framework/strip_name_scope.md): Removes name scope from a name.

[`variable(...)`](../../tf/contrib/framework/variable.md): Gets an existing variable with these parameters or creates a new one.

[`with_same_shape(...)`](../../tf/contrib/framework/with_same_shape.md): Assert tensors are the same shape, from the same graph.

[`with_shape(...)`](../../tf/contrib/framework/with_shape.md): Asserts tensor has expected shape.

[`zero_initializer(...)`](../../tf/contrib/framework/zero_initializer.md): Initialize 'ref' with all zeros, ref tensor should be uninitialized.

