<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.decode_jpeg" />
</div>

# tf.image.decode_jpeg

``` python
decode_jpeg(
    contents,
    channels=0,
    ratio=1,
    fancy_upscaling=True,
    try_recover_truncated=False,
    acceptable_fraction=1,
    dct_method='',
    name=None
)
```



Defined in `tensorflow/python/ops/gen_image_ops.py`.

See the guide: [Images > Encoding and Decoding](../../../../api_guides/python/image.md#Encoding_and_Decoding)

Decode a JPEG-encoded image to a uint8 tensor.

The attr `channels` indicates the desired number of color channels for the
decoded image.

Accepted values are:

*   0: Use the number of channels in the JPEG-encoded image.
*   1: output a grayscale image.
*   3: output an RGB image.

If needed, the JPEG-encoded image is transformed to match the requested number
of color channels.

The attr `ratio` allows downscaling the image by an integer factor during
decoding.  Allowed values are: 1, 2, 4, and 8.  This is much faster than
downscaling the image later.


This op also supports decoding PNGs and non-animated GIFs since the interface is
the same, though it is cleaner to use `tf.image.decode_image`.

#### Args:

* <b>`contents`</b>: A `Tensor` of type `string`. 0-D.  The JPEG-encoded image.
* <b>`channels`</b>: An optional `int`. Defaults to `0`.
    Number of color channels for the decoded image.
* <b>`ratio`</b>: An optional `int`. Defaults to `1`. Downscaling ratio.
* <b>`fancy_upscaling`</b>: An optional `bool`. Defaults to `True`.
    If true use a slower but nicer upscaling of the
    chroma planes (yuv420/422 only).
* <b>`try_recover_truncated`</b>: An optional `bool`. Defaults to `False`.
    If true try to recover an image from truncated input.
* <b>`acceptable_fraction`</b>: An optional `float`. Defaults to `1`.
    The minimum required fraction of lines before a truncated
    input is accepted.
* <b>`dct_method`</b>: An optional `string`. Defaults to `""`.
    string specifying a hint about the algorithm used for
    decompression.  Defaults to "" which maps to a system-specific
    default.  Currently valid values are ["INTEGER_FAST",
    "INTEGER_ACCURATE"].  The hint may be ignored (e.g., the internal
    jpeg library changes to a version that does not have that specific
    option.)
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `uint8`. 3-D with shape `[height, width, channels]`..