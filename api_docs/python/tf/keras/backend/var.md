<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.var" />
</div>

# tf.keras.backend.var

``` python
var(
    x,
    axis=None,
    keepdims=False
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Variance of a tensor, alongside the specified axis.

#### Arguments:

* <b>`x`</b>: A tensor or variable.
* <b>`axis`</b>: An integer, the axis to compute the variance.
* <b>`keepdims`</b>: A boolean, whether to keep the dimensions or not.
        If `keepdims` is `False`, the rank of the tensor is reduced
        by 1. If `keepdims` is `True`,
        the reduced dimension is retained with length 1.


#### Returns:

A tensor with the variance of elements of `x`.