<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.cast" />
</div>

# tf.keras.backend.cast

``` python
cast(
    x,
    dtype
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Casts a tensor to a different dtype and returns it.

You can cast a Keras variable but it still returns a Keras tensor.

#### Arguments:

* <b>`x`</b>: Keras tensor (or variable).
* <b>`dtype`</b>: String, either (`'float16'`, `'float32'`, or `'float64'`).


#### Returns:

    Keras tensor with dtype `dtype`.

Example:
```python
    >>> from keras import backend as K
    >>> input = K.placeholder((2, 3), dtype='float32')
    >>> input
    <tf.Tensor 'Placeholder_2:0' shape=(2, 3) dtype=float32>
    # It doesn't work in-place as below.
    >>> K.cast(input, dtype='float16')
    <tf.Tensor 'Cast_1:0' shape=(2, 3) dtype=float16>
    >>> input
    <tf.Tensor 'Placeholder_2:0' shape=(2, 3) dtype=float32>
    # you need to assign it.
    >>> input = K.cast(input, dtype='float16')
    >>> input
    <tf.Tensor 'Cast_2:0' shape=(2, 3) dtype=float16>
```