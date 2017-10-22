<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image" />
</div>

# Module: tf.image



Defined in [`tensorflow/python/ops/image_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/image_ops.py).

Image processing and decoding ops.

See the [Images](../../../api_guides/python/image.md) guide.



## Classes

[`class ResizeMethod`](../tf/image/ResizeMethod.md)

## Functions

[`adjust_brightness(...)`](../tf/image/adjust_brightness.md): Adjust the brightness of RGB or Grayscale images.

[`adjust_contrast(...)`](../tf/image/adjust_contrast.md): Adjust contrast of RGB or grayscale images.

[`adjust_gamma(...)`](../tf/image/adjust_gamma.md): Performs Gamma Correction on the input image.

[`adjust_hue(...)`](../tf/image/adjust_hue.md): Adjust hue of an RGB image.

[`adjust_saturation(...)`](../tf/image/adjust_saturation.md): Adjust saturation of an RGB image.

[`central_crop(...)`](../tf/image/central_crop.md): Crop the central region of the image.

[`convert_image_dtype(...)`](../tf/image/convert_image_dtype.md): Convert `image` to `dtype`, scaling its values if needed.

[`crop_and_resize(...)`](../tf/image/crop_and_resize.md): Extracts crops from the input image tensor and bilinearly resizes them (possibly

[`crop_to_bounding_box(...)`](../tf/image/crop_to_bounding_box.md): Crops an image to a specified bounding box.

[`decode_and_crop_jpeg(...)`](../tf/image/decode_and_crop_jpeg.md): Decode and Crop a JPEG-encoded image to a uint8 tensor.

[`decode_bmp(...)`](../tf/image/decode_bmp.md): Decode the first frame of a BMP-encoded image to a uint8 tensor.

[`decode_gif(...)`](../tf/image/decode_gif.md): Decode the first frame of a GIF-encoded image to a uint8 tensor.

[`decode_image(...)`](../tf/image/decode_image.md): Convenience function for `decode_bmp`, `decode_gif`, `decode_jpeg`,

[`decode_jpeg(...)`](../tf/image/decode_jpeg.md): Decode a JPEG-encoded image to a uint8 tensor.

[`decode_png(...)`](../tf/image/decode_png.md): Decode a PNG-encoded image to a uint8 or uint16 tensor.

[`draw_bounding_boxes(...)`](../tf/image/draw_bounding_boxes.md): Draw bounding boxes on a batch of images.

[`encode_jpeg(...)`](../tf/image/encode_jpeg.md): JPEG-encode an image.

[`encode_png(...)`](../tf/image/encode_png.md): PNG-encode an image.

[`extract_glimpse(...)`](../tf/image/extract_glimpse.md): Extracts a glimpse from the input tensor.

[`extract_jpeg_shape(...)`](../tf/image/extract_jpeg_shape.md): Extract the shape information of a JPEG-encoded image.

[`flip_left_right(...)`](../tf/image/flip_left_right.md): Flip an image horizontally (left to right).

[`flip_up_down(...)`](../tf/image/flip_up_down.md): Flip an image vertically (upside down).

[`grayscale_to_rgb(...)`](../tf/image/grayscale_to_rgb.md): Converts one or more images from Grayscale to RGB.

[`hsv_to_rgb(...)`](../tf/image/hsv_to_rgb.md): Convert one or more images from HSV to RGB.

[`non_max_suppression(...)`](../tf/image/non_max_suppression.md): Greedily selects a subset of bounding boxes in descending order of score.

[`pad_to_bounding_box(...)`](../tf/image/pad_to_bounding_box.md): Pad `image` with zeros to the specified `height` and `width`.

[`per_image_standardization(...)`](../tf/image/per_image_standardization.md): Linearly scales `image` to have zero mean and unit norm.

[`random_brightness(...)`](../tf/image/random_brightness.md): Adjust the brightness of images by a random factor.

[`random_contrast(...)`](../tf/image/random_contrast.md): Adjust the contrast of an image by a random factor.

[`random_flip_left_right(...)`](../tf/image/random_flip_left_right.md): Randomly flip an image horizontally (left to right).

[`random_flip_up_down(...)`](../tf/image/random_flip_up_down.md): Randomly flips an image vertically (upside down).

[`random_hue(...)`](../tf/image/random_hue.md): Adjust the hue of an RGB image by a random factor.

[`random_saturation(...)`](../tf/image/random_saturation.md): Adjust the saturation of an RGB image by a random factor.

[`resize_area(...)`](../tf/image/resize_area.md): Resize `images` to `size` using area interpolation.

[`resize_bicubic(...)`](../tf/image/resize_bicubic.md): Resize `images` to `size` using bicubic interpolation.

[`resize_bilinear(...)`](../tf/image/resize_bilinear.md): Resize `images` to `size` using bilinear interpolation.

[`resize_image_with_crop_or_pad(...)`](../tf/image/resize_image_with_crop_or_pad.md): Crops and/or pads an image to a target width and height.

[`resize_images(...)`](../tf/image/resize_images.md): Resize `images` to `size` using the specified `method`.

[`resize_nearest_neighbor(...)`](../tf/image/resize_nearest_neighbor.md): Resize `images` to `size` using nearest neighbor interpolation.

[`rgb_to_grayscale(...)`](../tf/image/rgb_to_grayscale.md): Converts one or more images from RGB to Grayscale.

[`rgb_to_hsv(...)`](../tf/image/rgb_to_hsv.md): Converts one or more images from RGB to HSV.

[`rot90(...)`](../tf/image/rot90.md): Rotate an image counter-clockwise by 90 degrees.

[`sample_distorted_bounding_box(...)`](../tf/image/sample_distorted_bounding_box.md): Generate a single randomly distorted bounding box for an image.

[`total_variation(...)`](../tf/image/total_variation.md): Calculate and return the total variation for one or more images.

[`transpose_image(...)`](../tf/image/transpose_image.md): Transpose an image by swapping the first and second dimension.

