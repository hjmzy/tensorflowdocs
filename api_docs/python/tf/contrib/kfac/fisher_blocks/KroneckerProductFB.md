<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.fisher_blocks.KroneckerProductFB" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="full_fisher_block"/>
<meta itemprop="property" content="instantiate_factors"/>
<meta itemprop="property" content="multiply"/>
<meta itemprop="property" content="multiply_inverse"/>
<meta itemprop="property" content="tensors_to_compute_grads"/>
</div>

# tf.contrib.kfac.fisher_blocks.KroneckerProductFB

## Class `KroneckerProductFB`

Inherits From: [`FisherBlock`](../../../../tf/contrib/kfac/fisher_blocks/FisherBlock.md)



Defined in [`tensorflow/contrib/kfac/python/ops/fisher_blocks.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/fisher_blocks.py).

A base class for FisherBlocks with separate input and output factors.

The Fisher block is approximated as a Kronecker product of the input and
output factors.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(layer_collection)
```



<h3 id="full_fisher_block"><code>full_fisher_block</code></h3>

``` python
full_fisher_block()
```

Explicitly constructs the full Fisher block.

Used for testing purposes. (In general, the result may be very large.)

#### Returns:

The full Fisher block.

<h3 id="instantiate_factors"><code>instantiate_factors</code></h3>

``` python
instantiate_factors(
    grads_list,
    damping
)
```

Creates and registers the component factors of this Fisher block.

#### Args:

* <b>`grads_list`</b>: A list gradients (each a Tensor or tuple of Tensors) with
      respect to the tensors returned by tensors_to_compute_grads() that
      are to be used to estimate the block.
* <b>`damping`</b>: The damping factor (float or Tensor).

<h3 id="multiply"><code>multiply</code></h3>

``` python
multiply(vector)
```



<h3 id="multiply_inverse"><code>multiply_inverse</code></h3>

``` python
multiply_inverse(vector)
```



<h3 id="tensors_to_compute_grads"><code>tensors_to_compute_grads</code></h3>

``` python
tensors_to_compute_grads()
```

Returns the Tensor(s) with respect to which this FisherBlock needs grads.
    



