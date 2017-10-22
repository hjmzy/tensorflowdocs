<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.utils.layer_params_to_mat2d" />
</div>

# tf.contrib.kfac.utils.layer_params_to_mat2d

``` python
layer_params_to_mat2d(vector)
```



Defined in [`tensorflow/contrib/kfac/python/ops/utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/utils.py).

Converts a vector shaped like layer parameters to a 2D matrix.

In particular, we reshape the weights/filter component of the vector to be
2D, flattening all leading (input) dimensions. If there is a bias component,
we concatenate it to the reshaped weights/filter component.

#### Args:

* <b>`vector`</b>: A Tensor or pair of Tensors shaped like layer parameters.


#### Returns:

A 2D Tensor with the same coefficients and the same output dimension.