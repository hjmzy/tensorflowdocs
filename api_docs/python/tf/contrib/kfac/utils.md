<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.utils" />
<meta itemprop="property" content="posdef_inv_funcs"/>
</div>

# Module: tf.contrib.kfac.utils



Defined in [`tensorflow/contrib/kfac/python/ops/utils_lib.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/utils_lib.py).

Utility functions.

## Classes

[`class SequenceDict`](../../../tf/contrib/kfac/utils/SequenceDict.md): A dict convenience wrapper that allows getting/setting with sequences.

[`class SubGraph`](../../../tf/contrib/kfac/utils/SubGraph.md): Defines a subgraph given by all the dependencies of a given set of outputs.

## Functions

[`column_to_tensors(...)`](../../../tf/contrib/kfac/utils/column_to_tensors.md): Converts a column vector back to the shape of the given template.

[`compute_pi(...)`](../../../tf/contrib/kfac/utils/compute_pi.md): Computes the scalar constant pi for Tikhonov regularization/damping.

[`fwd_gradients(...)`](../../../tf/contrib/kfac/utils/fwd_gradients.md): Compute forward-mode gradients.

[`generate_random_signs(...)`](../../../tf/contrib/kfac/utils/generate_random_signs.md): Generate a random tensor with {-1, +1} entries.

[`kronecker_product(...)`](../../../tf/contrib/kfac/utils/kronecker_product.md): Computes the Kronecker product two matrices.

[`layer_params_to_mat2d(...)`](../../../tf/contrib/kfac/utils/layer_params_to_mat2d.md): Converts a vector shaped like layer parameters to a 2D matrix.

[`mat2d_to_layer_params(...)`](../../../tf/contrib/kfac/utils/mat2d_to_layer_params.md): Converts a canonical 2D matrix representation back to a vector.

[`posdef_inv(...)`](../../../tf/contrib/kfac/utils/posdef_inv.md): Computes the inverse of tensor + damping * identity.

[`posdef_inv_cholesky(...)`](../../../tf/contrib/kfac/utils/posdef_inv_cholesky.md): Computes inverse(tensor + damping * identity) with Cholesky.

[`posdef_inv_matrix_inverse(...)`](../../../tf/contrib/kfac/utils/posdef_inv_matrix_inverse.md): Computes inverse(tensor + damping * identity) directly.

[`setdefault(...)`](../../../tf/contrib/kfac/utils/setdefault.md): Like dict.setdefault but delays evaluation of the value to be set.

[`tensors_to_column(...)`](../../../tf/contrib/kfac/utils/tensors_to_column.md): Converts a tensor or list of tensors to a column vector.

## Other Members

`posdef_inv_funcs`

