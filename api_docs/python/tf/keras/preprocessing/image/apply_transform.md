<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.apply_transform" />
</div>

# tf.keras.preprocessing.image.apply_transform

``` python
apply_transform(
    x,
    transform_matrix,
    channel_axis=0,
    fill_mode='nearest',
    cval=0.0
)
```



Defined in [`tensorflow/python/keras/_impl/keras/preprocessing/image.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/preprocessing/image.py).

Apply the image transformation specified by a matrix.

#### Arguments:

* <b>`x`</b>: 2D numpy array, single image.
* <b>`transform_matrix`</b>: Numpy array specifying the geometric transformation.
* <b>`channel_axis`</b>: Index of axis for channels in the input tensor.
* <b>`fill_mode`</b>: Points outside the boundaries of the input
        are filled according to the given mode
        (one of `{'constant', 'nearest', 'reflect', 'wrap'}`).
* <b>`cval`</b>: Value used for points outside the boundaries
        of the input if `mode='constant'`.


#### Returns:

The transformed version of the input.