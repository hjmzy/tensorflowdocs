<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.string_join" />
</div>

# tf.string_join

``` python
string_join(
    inputs,
    separator='',
    name=None
)
```



Defined in `tensorflow/python/ops/gen_string_ops.py`.

See the guide: [Strings > Joining](../../../api_guides/python/string_ops.md#Joining)

Joins the strings in the given list of string tensors into one tensor;

with the given separator (default is an empty separator).

#### Args:

* <b>`inputs`</b>: A list of at least 1 `Tensor` objects with type `string`.
    A list of string tensors.  The tensors must all have the same shape,
    or be scalars.  Scalars may be mixed in; these will be broadcast to the shape
    of non-scalar inputs.
* <b>`separator`</b>: An optional `string`. Defaults to `""`.
    string, an optional join separator.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`.