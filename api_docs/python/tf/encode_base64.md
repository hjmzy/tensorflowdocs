<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.encode_base64" />
</div>

# tf.encode_base64

``` python
encode_base64(
    input,
    pad=False,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_string_ops.py`.

See the guide: [Strings > Conversion](../../../api_guides/python/string_ops.md#Conversion)

Encode strings into web-safe base64 format.

Refer to the following article for more information on base64 format:
en.wikipedia.org/wiki/Base64. Base64 strings may have padding with '=' at the
end so that the encoded has length multiple of 4. See Padding section of the
link above.

Web-safe means that the encoder uses - and _ instead of + and /.

#### Args:

* <b>`input`</b>: A `Tensor` of type `string`. Strings to be encoded.
* <b>`pad`</b>: An optional `bool`. Defaults to `False`.
    Bool whether padding is applied at the ends.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`. Input strings encoded in base64.