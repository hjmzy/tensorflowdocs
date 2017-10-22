<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_blocks.FullyConnectedDiagonalFB" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="instantiate_factors"/>
<meta itemprop="property" content="multiply"/>
<meta itemprop="property" content="multiply_inverse"/>
<meta itemprop="property" content="register_additional_minibatch"/>
<meta itemprop="property" content="tensors_to_compute_grads"/>
</div>

# tf.contrib.kfac.fisher_blocks.FullyConnectedDiagonalFB

## Class `FullyConnectedDiagonalFB`

Inherits From: [`FisherBlock`](../../../../tf/contrib/kfac/fisher_blocks/FisherBlock.md)



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_blocks.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_blocks.py).

FisherBlock for fully-connected (dense) layers using a diagonal approx.

Estimates the Fisher Information matrix's diagonal entries for a fully
connected layer. Unlike NaiveDiagonalFB this uses the low-variance "sum of
squares" estimator.

Let 'params' be a vector parameterizing a model and 'i' an arbitrary index
into it. We are interested in Fisher(params)[i, i]. This is,

  Fisher(params)[i, i] = E[ v(x, y, params) v(x, y, params)^T ][i, i]
                       = E[ v(x, y, params)[i] ^ 2 ]

Consider fully connected layer in this model with (unshared) weight matrix
'w'. For an example 'x' that produces layer inputs 'a' and output
preactivations 's',

  v(x, y, w) = vec( x (d loss / d s)^T )

This FisherBlock tracks Fisher(params)[i, i] for all indices 'i' corresponding
to the layer's parameters 'w'.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    layer_collection,
    has_bias=False
)
```

Creates a FullyConnectedDiagonalFB block.

#### Args:

* <b>`layer_collection`</b>: The collection of all layers in the K-FAC approximate
      Fisher information matrix to which this FisherBlock belongs.
* <b>`has_bias`</b>: Whether the component Kronecker factors have an additive bias.
      (Default: False)

<h3 id="instantiate_factors"><code>instantiate_factors</code></h3>

``` python
instantiate_factors(
    grads_list,
    damping
)
```



<h3 id="multiply"><code>multiply</code></h3>

``` python
multiply(vector)
```

Approximate damped Fisher-vector product.

#### Args:

* <b>`vector`</b>: Tensor or 2-tuple of Tensors. if self._has_bias, Tensor of shape
    [input_size, output_size] corresponding to layer's weights. If not, a
    2-tuple of the former and a Tensor of shape [output_size] corresponding
    to the layer's bias.


#### Returns:

Tensor of the same shape, corresponding to the Fisher-vector product.

<h3 id="multiply_inverse"><code>multiply_inverse</code></h3>

``` python
multiply_inverse(vector)
```

Approximate damped inverse Fisher-vector product.

#### Args:

* <b>`vector`</b>: Tensor or 2-tuple of Tensors. if self._has_bias, Tensor of shape
    [input_size, output_size] corresponding to layer's weights. If not, a
    2-tuple of the former and a Tensor of shape [output_size] corresponding
    to the layer's bias.


#### Returns:

Tensor of the same shape, corresponding to the inverse Fisher-vector
product.

<h3 id="register_additional_minibatch"><code>register_additional_minibatch</code></h3>

``` python
register_additional_minibatch(
    inputs,
    outputs
)
```

Registers an additional minibatch to the FisherBlock.

#### Args:

* <b>`inputs`</b>: Tensor of shape [batch_size, input_size]. Inputs to the
    matrix-multiply.
* <b>`outputs`</b>: Tensor of shape [batch_size, output_size]. Layer preactivations.

<h3 id="tensors_to_compute_grads"><code>tensors_to_compute_grads</code></h3>

``` python
tensors_to_compute_grads()
```

Tensors to compute derivative of loss with respect to.



