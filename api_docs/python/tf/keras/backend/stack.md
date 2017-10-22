<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.stack" />
</div>

# tf.keras.backend.stack

``` python
stack(
    x,
    axis=0
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Stacks a list of rank `R` tensors into a rank `R+1` tensor.

#### Arguments:

* <b>`x`</b>: List of tensors.
* <b>`axis`</b>: Axis along which to perform stacking.


#### Returns:

A tensor.