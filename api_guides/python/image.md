<!-- DO NOT EDIT! Automatically generated file. -->
# Images

Note: Functions taking `Tensor` arguments can also take anything accepted by
[`tf.convert_to_tensor`](../../api_docs/python/tf/convert_to_tensor.md).

[TOC]

<h2 id="Encoding_and_Decoding">Encoding and Decoding</h2>

TensorFlow provides Ops to decode and encode JPEG and PNG formats.  Encoded
images are represented by scalar string Tensors, decoded images by 3-D uint8
tensors of shape `[height, width, channels]`. (PNG also supports uint16.)

The encode and decode Ops apply to one image at a time.  Their input and output
are all of variable size.  If you need fixed size images, pass the output of
the decode Ops to one of the cropping and resizing Ops.

Note: The PNG encode and decode Ops support RGBA, but the conversions Ops
presently only support RGB, HSV, and GrayScale. Presently, the alpha channel has
to be stripped from the image and re-attached using slicing ops.

*   [`tf.image.decode_gif`](../../api_docs/python/tf/image/decode_gif.md)
*   [`tf.image.decode_jpeg`](../../api_docs/python/tf/image/decode_jpeg.md)
*   [`tf.image.encode_jpeg`](../../api_docs/python/tf/image/encode_jpeg.md)
*   [`tf.image.decode_png`](../../api_docs/python/tf/image/decode_png.md)
*   [`tf.image.encode_png`](../../api_docs/python/tf/image/encode_png.md)
*   [`tf.image.decode_image`](../../api_docs/python/tf/image/decode_image.md)

<h2 id="Resizing">Resizing</h2>

The resizing Ops accept input images as tensors of several types.  They always
output resized images as float32 tensors.

The convenience function [`tf.image.resize_images`](../../api_docs/python/tf/image/resize_images.md) supports both 4-D
and 3-D tensors as input and output.  4-D tensors are for batches of images,
3-D tensors for individual images.

Other resizing Ops only support 4-D batches of images as input:
[`tf.image.resize_area`](../../api_docs/python/tf/image/resize_area.md), [`tf.image.resize_bicubic`](../../api_docs/python/tf/image/resize_bicubic.md),
[`tf.image.resize_bilinear`](../../api_docs/python/tf/image/resize_bilinear.md),
[`tf.image.resize_nearest_neighbor`](../../api_docs/python/tf/image/resize_nearest_neighbor.md).

Example:

```python
# Decode a JPG image and resize it to 299 by 299 using default method.
image = tf.image.decode_jpeg(...)
resized_image = tf.image.resize_images(image, [299, 299])
```

*   [`tf.image.resize_images`](../../api_docs/python/tf/image/resize_images.md)
*   [`tf.image.resize_area`](../../api_docs/python/tf/image/resize_area.md)
*   [`tf.image.resize_bicubic`](../../api_docs/python/tf/image/resize_bicubic.md)
*   [`tf.image.resize_bilinear`](../../api_docs/python/tf/image/resize_bilinear.md)
*   [`tf.image.resize_nearest_neighbor`](../../api_docs/python/tf/image/resize_nearest_neighbor.md)

<h2 id="Cropping">Cropping</h2>

*   [`tf.image.resize_image_with_crop_or_pad`](../../api_docs/python/tf/image/resize_image_with_crop_or_pad.md)
*   [`tf.image.central_crop`](../../api_docs/python/tf/image/central_crop.md)
*   [`tf.image.pad_to_bounding_box`](../../api_docs/python/tf/image/pad_to_bounding_box.md)
*   [`tf.image.crop_to_bounding_box`](../../api_docs/python/tf/image/crop_to_bounding_box.md)
*   [`tf.image.extract_glimpse`](../../api_docs/python/tf/image/extract_glimpse.md)
*   [`tf.image.crop_and_resize`](../../api_docs/python/tf/image/crop_and_resize.md)

<h2 id="Flipping_Rotating_and_Transposing">Flipping, Rotating and Transposing</h2>

*   [`tf.image.flip_up_down`](../../api_docs/python/tf/image/flip_up_down.md)
*   [`tf.image.random_flip_up_down`](../../api_docs/python/tf/image/random_flip_up_down.md)
*   [`tf.image.flip_left_right`](../../api_docs/python/tf/image/flip_left_right.md)
*   [`tf.image.random_flip_left_right`](../../api_docs/python/tf/image/random_flip_left_right.md)
*   [`tf.image.transpose_image`](../../api_docs/python/tf/image/transpose_image.md)
*   [`tf.image.rot90`](../../api_docs/python/tf/image/rot90.md)

<h2 id="Converting_Between_Colorspaces">Converting Between Colorspaces</h2>

Image ops work either on individual images or on batches of images, depending on
the shape of their input Tensor.

If 3-D, the shape is `[height, width, channels]`, and the Tensor represents one
image. If 4-D, the shape is `[batch_size, height, width, channels]`, and the
Tensor represents `batch_size` images.

Currently, `channels` can usefully be 1, 2, 3, or 4. Single-channel images are
grayscale, images with 3 channels are encoded as either RGB or HSV. Images
with 2 or 4 channels include an alpha channel, which has to be stripped from the
image before passing the image to most image processing functions (and can be
re-attached later).

Internally, images are either stored in as one `float32` per channel per pixel
(implicitly, values are assumed to lie in `[0,1)`) or one `uint8` per channel
per pixel (values are assumed to lie in `[0,255]`).

TensorFlow can convert between images in RGB or HSV. The conversion functions
work only on float images, so you need to convert images in other formats using
[`tf.image.convert_image_dtype`](../../api_docs/python/tf/image/convert_image_dtype.md).

Example:

```python
# Decode an image and convert it to HSV.
rgb_image = tf.image.decode_png(...,  channels=3)
rgb_image_float = tf.image.convert_image_dtype(rgb_image, tf.float32)
hsv_image = tf.image.rgb_to_hsv(rgb_image)
```

*   [`tf.image.rgb_to_grayscale`](../../api_docs/python/tf/image/rgb_to_grayscale.md)
*   [`tf.image.grayscale_to_rgb`](../../api_docs/python/tf/image/grayscale_to_rgb.md)
*   [`tf.image.hsv_to_rgb`](../../api_docs/python/tf/image/hsv_to_rgb.md)
*   [`tf.image.rgb_to_hsv`](../../api_docs/python/tf/image/rgb_to_hsv.md)
*   [`tf.image.convert_image_dtype`](../../api_docs/python/tf/image/convert_image_dtype.md)

<h2 id="Image_Adjustments">Image Adjustments</h2>

TensorFlow provides functions to adjust images in various ways: brightness,
contrast, hue, and saturation.  Each adjustment can be done with predefined
parameters or with random parameters picked from predefined intervals. Random
adjustments are often useful to expand a training set and reduce overfitting.

If several adjustments are chained it is advisable to minimize the number of
redundant conversions by first converting the images to the most natural data
type and representation (RGB or HSV).

*   [`tf.image.adjust_brightness`](../../api_docs/python/tf/image/adjust_brightness.md)
*   [`tf.image.random_brightness`](../../api_docs/python/tf/image/random_brightness.md)
*   [`tf.image.adjust_contrast`](../../api_docs/python/tf/image/adjust_contrast.md)
*   [`tf.image.random_contrast`](../../api_docs/python/tf/image/random_contrast.md)
*   [`tf.image.adjust_hue`](../../api_docs/python/tf/image/adjust_hue.md)
*   [`tf.image.random_hue`](../../api_docs/python/tf/image/random_hue.md)
*   [`tf.image.adjust_gamma`](../../api_docs/python/tf/image/adjust_gamma.md)
*   [`tf.image.adjust_saturation`](../../api_docs/python/tf/image/adjust_saturation.md)
*   [`tf.image.random_saturation`](../../api_docs/python/tf/image/random_saturation.md)
*   [`tf.image.per_image_standardization`](../../api_docs/python/tf/image/per_image_standardization.md)

<h2 id="Working_with_Bounding_Boxes">Working with Bounding Boxes</h2>

*   [`tf.image.draw_bounding_boxes`](../../api_docs/python/tf/image/draw_bounding_boxes.md)
*   [`tf.image.non_max_suppression`](../../api_docs/python/tf/image/non_max_suppression.md)
*   [`tf.image.sample_distorted_bounding_box`](../../api_docs/python/tf/image/sample_distorted_bounding_box.md)

<h2 id="Denoising">Denoising</h2>

*   [`tf.image.total_variation`](../../api_docs/python/tf/image/total_variation.md)
