<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.l1_l2_regularizer" />
</div>

# tf.contrib.layers.l1_l2_regularizer

``` python
l1_l2_regularizer(
    scale_l1=1.0,
    scale_l2=1.0,
    scope=None
)
```



Defined in [`tensorflow/contrib/layers/python/layers/regularizers.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/regularizers.py).

Returns a function that can be used to apply L1 L2 regularizations.

#### Args:

* <b>`scale_l1`</b>: A scalar multiplier `Tensor` for L1 regularization.
* <b>`scale_l2`</b>: A scalar multiplier `Tensor` for L2 regularization.
* <b>`scope`</b>: An optional scope name.


#### Returns:

A function with signature `l1_l2(weights)` that applies a weighted sum of
L1 L2 regularization.


#### Raises:

* <b>`ValueError`</b>: If scale is negative or if scale is not a float.