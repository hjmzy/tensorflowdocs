<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.eval.image_reshaper" />
</div>

# tf.contrib.gan.eval.image_reshaper

### Aliases:

* `tf.contrib.gan.eval.eval_utils.image_reshaper`
* `tf.contrib.gan.eval.image_reshaper`

``` python
image_reshaper(
    images,
    num_cols=None
)
```



Defined in [`tensorflow/contrib/gan/python/eval/python/eval_utils_impl.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/eval/python/eval_utils_impl.py).

A reshaped summary image.

Returns an image that will contain all elements in the list and will be
laid out in a nearly-square tiling pattern (e.g. 11 images will lead to a
3x4 tiled image).

#### Args:

* <b>`images`</b>: Image data to summarize. Can be an RGB or grayscale image, a list of
       such images, or a set of RGB images concatenated along the depth
       dimension. The shape of each image is assumed to be [batch_size,
       height, width, depth].
* <b>`num_cols`</b>: (Optional) If provided, this is the number of columns in the final
       output image grid. Otherwise, the number of columns is determined by
       the number of images.


#### Returns:

A summary image matching the input with automatic tiling if needed.
Output shape is [1, height, width, channels].