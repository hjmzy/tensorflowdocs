<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.image.translate" />
</div>

# tf.contrib.image.translate

``` python
translate(
    images,
    translations,
    interpolation='NEAREST',
    name=None
)
```



Defined in [`tensorflow/contrib/image/python/ops/image_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/image/python/ops/image_ops.py).

Translate image(s) by the passed vectors(s).

#### Args:

* <b>`images`</b>: A tensor of shape (num_images, num_rows, num_columns, num_channels)
      (NHWC), (num_rows, num_columns, num_channels) (HWC), or
      (num_rows, num_columns) (HW). The rank must be statically known (the
      shape is not `TensorShape(None)`.
* <b>`translations`</b>: A vector representing [dx, dy] or (if images has rank 4)
      a matrix of length num_images, with a [dx, dy] vector for each image in
      the batch.
* <b>`interpolation`</b>: Interpolation mode. Supported values: "NEAREST", "BILINEAR".
* <b>`name`</b>: The name of the op.


#### Returns:

Image(s) with the same type and shape as `images`, translated by the given
    vector(s). Empty space due to the translation will be filled with zeros.


#### Raises:

* <b>`TypeError`</b>: If `image` is an invalid type.