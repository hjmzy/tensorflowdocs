<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.int_shape" />
</div>

# tf.keras.backend.int_shape

``` python
int_shape(x)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Returns the shape tensor or variable as a tuple of int or None entries.

#### Arguments:

* <b>`x`</b>: Tensor or variable.


#### Returns:

    A tuple of integers (or None entries).

Examples:
```python
    >>> from keras import backend as K
    >>> input = K.placeholder(shape=(2, 4, 5))
    >>> K.int_shape(input)
    (2, 4, 5)
    >>> val = np.array([[1, 2], [3, 4]])
    >>> kvar = K.variable(value=val)
    >>> K.int_shape(kvar)
    (2, 2)
```