<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_factors.FullyConnectedDiagonalFactor" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_cov"/>
<meta itemprop="property" content="instantiate_covariance"/>
<meta itemprop="property" content="make_covariance_update_op"/>
<meta itemprop="property" content="make_inverse_update_ops"/>
</div>

# tf.contrib.kfac.fisher_factors.FullyConnectedDiagonalFactor

## Class `FullyConnectedDiagonalFactor`

Inherits From: [`DiagonalFactor`](../../../../tf/contrib/kfac/fisher_factors/DiagonalFactor.md)



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_factors.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_factors.py).

FisherFactor for a diagonal approx of a fully-connected layer's Fisher.

Given in = [batch_size, input_size] and out_grad = [batch_size, output_size],
approximates the covariance as,

  Cov(in, out) = (1/batch_size) \sum_{i} outer(in[i], out_grad[i]) ** 2.0

where the square is taken element-wise.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    inputs,
    outputs_grads,
    has_bias=False
)
```

Instantiate FullyConnectedDiagonalFactor.

#### Args:

* <b>`inputs`</b>: Tensor of shape [batch_size, input_size]. Inputs to fully
    connected layer.
* <b>`outputs_grads`</b>: List of Tensors of shape [batch_size, output_size].
    Gradient of loss with respect to layer's preactivations.
* <b>`has_bias`</b>: bool. If True, append '1' to each input.

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



