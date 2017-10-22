<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_factors.ConvDiagonalFactor" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_cov"/>
<meta itemprop="property" content="instantiate_covariance"/>
<meta itemprop="property" content="make_covariance_update_op"/>
<meta itemprop="property" content="make_inverse_update_ops"/>
</div>

# tf.contrib.kfac.fisher_factors.ConvDiagonalFactor

## Class `ConvDiagonalFactor`

Inherits From: [`DiagonalFactor`](../../../../tf/contrib/kfac/fisher_factors/DiagonalFactor.md)



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_factors.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_factors.py).

FisherFactor for a diagonal approx of a convolutional layer's Fisher.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    inputs,
    outputs_grads,
    filter_shape,
    strides,
    padding,
    has_bias=False
)
```

Creates a ConvDiagonalFactor object.

#### Args:

* <b>`inputs`</b>: Tensor of shape [batch_size, height, width, in_channels].
    Input activations to this layer.
* <b>`outputs_grads`</b>: Tensor of shape [batch_size, height, width, out_channels].
    Per-example gradients to the loss with respect to the layer's output
    preactivations.
* <b>`filter_shape`</b>: Tuple of 4 ints: (kernel_height, kernel_width, in_channels,
    out_channels). Represents shape of kernel used in this layer.
* <b>`strides`</b>: The stride size in this layer (1-D Tensor of length 4).
* <b>`padding`</b>: The padding in this layer (1-D of Tensor length 4).
* <b>`has_bias`</b>: Python bool. If True, the layer is assumed to have a bias
    parameter in addition to its filter parameter.

<h3 id="get_cov"><code>get_cov</code></h3>

``` python
get_cov()
```



<h3 id="instantiate_covariance"><code>instantiate_covariance</code></h3>

``` python
instantiate_covariance()
```

Instantiates the covariance Variable as the instance member _cov.

<h3 id="make_covariance_update_op"><code>make_covariance_update_op</code></h3>

``` python
make_covariance_update_op(ema_decay)
```

Constructs and returns the covariance update Op.

#### Args:

* <b>`ema_decay`</b>: The exponential moving average decay (float or Tensor).

#### Returns:

An Op for updating the covariance Variable referenced by _cov.

<h3 id="make_inverse_update_ops"><code>make_inverse_update_ops</code></h3>

``` python
make_inverse_update_ops()
```

Create and return update ops corresponding to registered computations.



