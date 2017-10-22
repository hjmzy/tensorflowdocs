<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.normalize" />
</div>

# tf.keras.utils.normalize

``` python
normalize(
    x,
    axis=-1,
    order=2
)
```



Defined in [`tensorflow/python/keras/_impl/keras/utils/np_utils.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/utils/np_utils.py).

Normalizes a Numpy array.

#### Arguments:

* <b>`x`</b>: Numpy array to normalize.
* <b>`axis`</b>: axis along which to normalize.
* <b>`order`</b>: Normalization order (e.g. 2 for L2 norm).


#### Returns:

A normalized copy of the array.