<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.cast_to_floatx" />
</div>

# tf.keras.backend.cast_to_floatx

``` python
cast_to_floatx(x)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Cast a Numpy array to the default Keras float type.

#### Arguments:

* <b>`x`</b>: Numpy array.


#### Returns:

    The same Numpy array, cast to its new type.

Example:
```python
    >>> from keras import backend as K
    >>> K.floatx()
    'float32'
    >>> arr = numpy.array([1.0, 2.0], dtype='float64')
    >>> arr.dtype
    dtype('float64')
    >>> new_arr = K.cast_to_floatx(arr)
    >>> new_arr
    array([ 1.,  2.], dtype=float32)
    >>> new_arr.dtype
    dtype('float32')
```