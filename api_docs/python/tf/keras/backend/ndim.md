<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.ndim" />
</div>

# tf.keras.backend.ndim

``` python
ndim(x)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Returns the number of axes in a tensor, as an integer.

#### Arguments:

* <b>`x`</b>: Tensor or variable.


#### Returns:

    Integer (scalar), number of axes.

Examples:
```python
    >>> from keras import backend as K
    >>> input = K.placeholder(shape=(2, 4, 5))
    >>> val = np.array([[1, 2], [3, 4]])
    >>> kvar = K.variable(value=val)
    >>> K.ndim(input)
    3
    >>> K.ndim(kvar)
    2
```