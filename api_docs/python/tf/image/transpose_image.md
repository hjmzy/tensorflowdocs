<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.transpose_image" />
</div>

# tf.image.transpose_image

``` python
transpose_image(image)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/image_ops_impl.py).

See the guide: [Images > Flipping, Rotating and Transposing](../../../../api_guides/python/image.md#Flipping_Rotating_and_Transposing)

Transpose an image by swapping the first and second dimension.

See also `transpose()`.

#### Args:

* <b>`image`</b>: 3-D tensor of shape `[height, width, channels]`


#### Returns:

A 3-D tensor of shape `[width, height, channels]`


#### Raises:

* <b>`ValueError`</b>: if the shape of `image` not supported.