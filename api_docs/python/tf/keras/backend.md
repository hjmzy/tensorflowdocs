<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend" />
</div>

# Module: tf.keras.backend



Defined in [`tensorflow/python/keras/backend/__init__.py`](https://www.tensorflow.org/code/tensorflow/python/keras/backend/__init__.py).

Keras backend API.

## Classes

[`class name_scope`](../../tf/name_scope.md): A context manager for use when defining a Python op.

## Functions

[`abs(...)`](../../tf/keras/backend/abs.md): Element-wise absolute value.

[`all(...)`](../../tf/keras/backend/all.md): Bitwise reduction (logical AND).

[`any(...)`](../../tf/keras/backend/any.md): Bitwise reduction (logical OR).

[`arange(...)`](../../tf/keras/backend/arange.md): Creates a 1D tensor containing a sequence of integers.

[`argmax(...)`](../../tf/keras/backend/argmax.md): Returns the index of the maximum value along an axis.

[`argmin(...)`](../../tf/keras/backend/argmin.md): Returns the index of the minimum value along an axis.

[`backend(...)`](../../tf/keras/backend/backend.md): Publicly accessible method for determining the current backend.

[`batch_dot(...)`](../../tf/keras/backend/batch_dot.md): Batchwise dot product.

[`batch_flatten(...)`](../../tf/keras/backend/batch_flatten.md): Turn a nD tensor into a 2D tensor with same 0th dimension.

[`batch_get_value(...)`](../../tf/keras/backend/batch_get_value.md): Returns the value of more than one tensor variable.

[`batch_normalization(...)`](../../tf/keras/backend/batch_normalization.md): Applies batch normalization on x given mean, var, beta and gamma.

[`batch_set_value(...)`](../../tf/keras/backend/batch_set_value.md): Sets the values of many tensor variables at once.

[`bias_add(...)`](../../tf/keras/backend/bias_add.md): Adds a bias vector to a tensor.

[`binary_crossentropy(...)`](../../tf/keras/backend/binary_crossentropy.md): Binary crossentropy between an output tensor and a target tensor.

[`cast(...)`](../../tf/keras/backend/cast.md): Casts a tensor to a different dtype and returns it.

[`cast_to_floatx(...)`](../../tf/keras/backend/cast_to_floatx.md): Cast a Numpy array to the default Keras float type.

[`categorical_crossentropy(...)`](../../tf/keras/backend/categorical_crossentropy.md): Categorical crossentropy between an output tensor and a target tensor.

[`clear_session(...)`](../../tf/keras/backend/clear_session.md): Destroys the current TF graph and creates a new one.

[`clip(...)`](../../tf/keras/backend/clip.md): Element-wise value clipping.

[`concatenate(...)`](../../tf/keras/backend/concatenate.md): Concatenates a list of tensors alongside the specified axis.

[`constant(...)`](../../tf/keras/backend/constant.md): Creates a constant tensor.

[`conv1d(...)`](../../tf/keras/backend/conv1d.md): 1D convolution.

[`conv2d(...)`](../../tf/keras/backend/conv2d.md): 2D convolution.

[`conv2d_transpose(...)`](../../tf/keras/backend/conv2d_transpose.md): 2D deconvolution (i.e.

[`conv3d(...)`](../../tf/keras/backend/conv3d.md): 3D convolution.

[`cos(...)`](../../tf/keras/backend/cos.md): Computes cos of x element-wise.

[`count_params(...)`](../../tf/keras/backend/count_params.md): Returns the number of scalars in a Keras variable.

[`ctc_batch_cost(...)`](../../tf/keras/backend/ctc_batch_cost.md): Runs CTC loss algorithm on each batch element.

[`ctc_decode(...)`](../../tf/keras/backend/ctc_decode.md): Decodes the output of a softmax.

[`ctc_label_dense_to_sparse(...)`](../../tf/keras/backend/ctc_label_dense_to_sparse.md): Converts CTC labels from dense to sparse.

[`dot(...)`](../../tf/keras/backend/dot.md): Multiplies 2 tensors (and/or variables) and returns a *tensor*.

[`dropout(...)`](../../tf/keras/backend/dropout.md): Sets entries in `x` to zero at random, while scaling the entire tensor.

[`dtype(...)`](../../tf/keras/backend/dtype.md): Returns the dtype of a Keras tensor or variable, as a string.

[`elu(...)`](../../tf/keras/backend/elu.md): Exponential linear unit.

[`epsilon(...)`](../../tf/keras/backend/epsilon.md): Returns the value of the fuzz factor used in numeric expressions.

[`equal(...)`](../../tf/keras/backend/equal.md): Element-wise equality between two tensors.

[`eval(...)`](../../tf/keras/backend/eval.md): Evaluates the value of a variable.

[`exp(...)`](../../tf/keras/backend/exp.md): Element-wise exponential.

[`expand_dims(...)`](../../tf/keras/backend/expand_dims.md): Adds a 1-sized dimension at index "axis".

[`eye(...)`](../../tf/keras/backend/eye.md): Instantiate an identity matrix and returns it.

[`flatten(...)`](../../tf/keras/backend/flatten.md): Flatten a tensor.

[`floatx(...)`](../../tf/keras/backend/floatx.md): Returns the default float type, as a string.

[`foldl(...)`](../../tf/keras/backend/foldl.md): Reduce elems using fn to combine them from left to right.

[`foldr(...)`](../../tf/keras/backend/foldr.md): Reduce elems using fn to combine them from right to left.

[`function(...)`](../../tf/keras/backend/function.md): Instantiates a Keras function.

[`gather(...)`](../../tf/keras/backend/gather.md): Retrieves the elements of indices `indices` in the tensor `reference`.

[`get_session(...)`](../../tf/keras/backend/get_session.md): Returns the TF session to be used by the backend.

[`get_uid(...)`](../../tf/keras/backend/get_uid.md): Associates a string prefix with an integer counter in a TensorFlow graph.

[`get_value(...)`](../../tf/keras/backend/get_value.md): Returns the value of a variable.

[`gradients(...)`](../../tf/keras/backend/gradients.md): Returns the gradients of `variables` w.r.t. `loss`.

[`greater(...)`](../../tf/keras/backend/greater.md): Element-wise truth value of (x > y).

[`greater_equal(...)`](../../tf/keras/backend/greater_equal.md): Element-wise truth value of (x >= y).

[`hard_sigmoid(...)`](../../tf/keras/backend/hard_sigmoid.md): Segment-wise linear approximation of sigmoid.

[`image_data_format(...)`](../../tf/keras/backend/image_data_format.md): Returns the default image data format convention.

[`in_test_phase(...)`](../../tf/keras/backend/in_test_phase.md): Selects `x` in test phase, and `alt` otherwise.

[`in_top_k(...)`](../../tf/keras/backend/in_top_k.md): Returns whether the `targets` are in the top `k` `predictions`.

[`in_train_phase(...)`](../../tf/keras/backend/in_train_phase.md): Selects `x` in train phase, and `alt` otherwise.

[`int_shape(...)`](../../tf/keras/backend/int_shape.md): Returns the shape tensor or variable as a tuple of int or None entries.

[`is_sparse(...)`](../../tf/keras/backend/is_sparse.md): Returns whether a tensor is a sparse tensor.

[`l2_normalize(...)`](../../tf/keras/backend/l2_normalize.md): Normalizes a tensor wrt the L2 norm alongside the specified axis.

[`learning_phase(...)`](../../tf/keras/backend/learning_phase.md): Returns the learning phase flag.

[`less(...)`](../../tf/keras/backend/less.md): Element-wise truth value of (x < y).

[`less_equal(...)`](../../tf/keras/backend/less_equal.md): Element-wise truth value of (x <= y).

[`log(...)`](../../tf/keras/backend/log.md): Element-wise log.

[`manual_variable_initialization(...)`](../../tf/keras/backend/manual_variable_initialization.md): Sets the manual variable initialization flag.

[`map_fn(...)`](../../tf/keras/backend/map_fn.md): Map the function fn over the elements elems and return the outputs.

[`max(...)`](../../tf/keras/backend/max.md): Maximum value in a tensor.

[`maximum(...)`](../../tf/keras/backend/maximum.md): Element-wise maximum of two tensors.

[`mean(...)`](../../tf/keras/backend/mean.md): Mean of a tensor, alongside the specified axis.

[`min(...)`](../../tf/keras/backend/min.md): Minimum value in a tensor.

[`minimum(...)`](../../tf/keras/backend/minimum.md): Element-wise minimum of two tensors.

[`moving_average_update(...)`](../../tf/keras/backend/moving_average_update.md): Compute the moving average of a variable.

[`ndim(...)`](../../tf/keras/backend/ndim.md): Returns the number of axes in a tensor, as an integer.

[`normalize_batch_in_training(...)`](../../tf/keras/backend/normalize_batch_in_training.md): Computes mean and std for batch then apply batch_normalization on batch.

[`not_equal(...)`](../../tf/keras/backend/not_equal.md): Element-wise inequality between two tensors.

[`one_hot(...)`](../../tf/keras/backend/one_hot.md): Computes the one-hot representation of an integer tensor.

[`ones(...)`](../../tf/keras/backend/ones.md): Instantiates an all-ones tensor variable and returns it.

[`ones_like(...)`](../../tf/keras/backend/ones_like.md): Instantiates an all-ones variable of the same shape as another tensor.

[`permute_dimensions(...)`](../../tf/keras/backend/permute_dimensions.md): Permutes axes in a tensor.

[`placeholder(...)`](../../tf/keras/backend/placeholder.md): Instantiates a placeholder tensor and returns it.

[`pool2d(...)`](../../tf/keras/backend/pool2d.md): 2D Pooling.

[`pool3d(...)`](../../tf/keras/backend/pool3d.md): 3D Pooling.

[`pow(...)`](../../tf/keras/backend/pow.md): Element-wise exponentiation.

[`print_tensor(...)`](../../tf/keras/backend/print_tensor.md): Prints `message` and the tensor value when evaluated.

[`prod(...)`](../../tf/keras/backend/prod.md): Multiplies the values in a tensor, alongside the specified axis.

[`random_binomial(...)`](../../tf/keras/backend/random_binomial.md): Returns a tensor with random binomial distribution of values.

[`random_normal(...)`](../../tf/keras/backend/random_normal.md): Returns a tensor with normal distribution of values.

[`random_normal_variable(...)`](../../tf/keras/backend/random_normal_variable.md): Instantiates a variable with values drawn from a normal distribution.

[`random_uniform(...)`](../../tf/keras/backend/random_uniform.md): Returns a tensor with uniform distribution of values.

[`random_uniform_variable(...)`](../../tf/keras/backend/random_uniform_variable.md): Instantiates a variable with values drawn from a uniform distribution.

[`relu(...)`](../../tf/keras/backend/relu.md): Rectified linear unit.

[`repeat(...)`](../../tf/keras/backend/repeat.md): Repeats a 2D tensor.

[`repeat_elements(...)`](../../tf/keras/backend/repeat_elements.md): Repeats the elements of a tensor along an axis, like `np.repeat`.

[`reset_uids(...)`](../../tf/keras/backend/reset_uids.md)

[`reshape(...)`](../../tf/keras/backend/reshape.md): Reshapes a tensor to the specified shape.

[`resize_images(...)`](../../tf/keras/backend/resize_images.md): Resizes the images contained in a 4D tensor.

[`resize_volumes(...)`](../../tf/keras/backend/resize_volumes.md): Resizes the volume contained in a 5D tensor.

[`reverse(...)`](../../tf/keras/backend/reverse.md): Reverse a tensor along the specified axes.

[`rnn(...)`](../../tf/keras/backend/rnn.md): Iterates over the time dimension of a tensor.

[`round(...)`](../../tf/keras/backend/round.md): Element-wise rounding to the closest integer.

[`separable_conv2d(...)`](../../tf/keras/backend/separable_conv2d.md): 2D convolution with separable filters.

[`set_epsilon(...)`](../../tf/keras/backend/set_epsilon.md): Sets the value of the fuzz factor used in numeric expressions.

[`set_floatx(...)`](../../tf/keras/backend/set_floatx.md): Sets the default float type.

[`set_image_data_format(...)`](../../tf/keras/backend/set_image_data_format.md): Sets the value of the image data format convention.

[`set_learning_phase(...)`](../../tf/keras/backend/set_learning_phase.md): Sets the learning phase to a fixed value.

[`set_session(...)`](../../tf/keras/backend/set_session.md): Sets the global TensorFlow session.

[`set_value(...)`](../../tf/keras/backend/set_value.md): Sets the value of a variable, from a Numpy array.

[`shape(...)`](../../tf/keras/backend/shape.md): Returns the symbolic shape of a tensor or variable.

[`sigmoid(...)`](../../tf/keras/backend/sigmoid.md): Element-wise sigmoid.

[`sign(...)`](../../tf/keras/backend/sign.md): Element-wise sign.

[`sin(...)`](../../tf/keras/backend/sin.md): Computes sin of x element-wise.

[`softmax(...)`](../../tf/keras/backend/softmax.md): Softmax of a tensor.

[`softplus(...)`](../../tf/keras/backend/softplus.md): Softplus of a tensor.

[`softsign(...)`](../../tf/keras/backend/softsign.md): Softsign of a tensor.

[`sparse_categorical_crossentropy(...)`](../../tf/keras/backend/sparse_categorical_crossentropy.md): Categorical crossentropy with integer targets.

[`spatial_2d_padding(...)`](../../tf/keras/backend/spatial_2d_padding.md): Pads the 2nd and 3rd dimensions of a 4D tensor.

[`spatial_3d_padding(...)`](../../tf/keras/backend/spatial_3d_padding.md): Pads 5D tensor with zeros along the depth, height, width dimensions.

[`sqrt(...)`](../../tf/keras/backend/sqrt.md): Element-wise square root.

[`square(...)`](../../tf/keras/backend/square.md): Element-wise square.

[`squeeze(...)`](../../tf/keras/backend/squeeze.md): Removes a 1-dimension from the tensor at index "axis".

[`stack(...)`](../../tf/keras/backend/stack.md): Stacks a list of rank `R` tensors into a rank `R+1` tensor.

[`std(...)`](../../tf/keras/backend/std.md): Standard deviation of a tensor, alongside the specified axis.

[`stop_gradient(...)`](../../tf/keras/backend/stop_gradient.md): Returns `variables` but with zero gradient w.r.t. every other variable.

[`sum(...)`](../../tf/keras/backend/sum.md): Sum of the values in a tensor, alongside the specified axis.

[`switch(...)`](../../tf/keras/backend/switch.md): Switches between two operations depending on a scalar value.

[`tanh(...)`](../../tf/keras/backend/tanh.md): Element-wise tanh.

[`temporal_padding(...)`](../../tf/keras/backend/temporal_padding.md): Pads the middle dimension of a 3D tensor.

[`to_dense(...)`](../../tf/keras/backend/to_dense.md): Converts a sparse tensor into a dense tensor and returns it.

[`transpose(...)`](../../tf/keras/backend/transpose.md): Transposes a tensor and returns it.

[`truncated_normal(...)`](../../tf/keras/backend/truncated_normal.md): Returns a tensor with truncated random normal distribution of values.

[`update(...)`](../../tf/keras/backend/update.md)

[`update_add(...)`](../../tf/keras/backend/update_add.md): Update the value of `x` by adding `increment`.

[`update_sub(...)`](../../tf/keras/backend/update_sub.md): Update the value of `x` by subtracting `decrement`.

[`var(...)`](../../tf/keras/backend/var.md): Variance of a tensor, alongside the specified axis.

[`variable(...)`](../../tf/keras/backend/variable.md): Instantiates a variable and returns it.

[`zeros(...)`](../../tf/keras/backend/zeros.md): Instantiates an all-zeros variable and returns it.

[`zeros_like(...)`](../../tf/keras/backend/zeros_like.md): Instantiates an all-zeros variable of the same shape as another tensor.

