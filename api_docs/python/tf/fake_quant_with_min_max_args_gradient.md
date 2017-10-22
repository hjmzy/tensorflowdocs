<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.fake_quant_with_min_max_args_gradient" />
</div>

# tf.fake_quant_with_min_max_args_gradient

``` python
fake_quant_with_min_max_args_gradient(
    gradients,
    inputs,
    min=-6,
    max=6,
    num_bits=8,
    narrow_range=False,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_array_ops.py`.

See the guide: [Tensor Transformations > Fake quantization](../../../api_guides/python/array_ops.md#Fake_quantization)

Compute gradients for a FakeQuantWithMinMaxArgs operation.

#### Args:

* <b>`gradients`</b>: A `Tensor` of type `float32`.
    Backpropagated gradients above the FakeQuantWithMinMaxArgs operation.
* <b>`inputs`</b>: A `Tensor` of type `float32`.
    Values passed as inputs to the FakeQuantWithMinMaxArgs operation.
* <b>`min`</b>: An optional `float`. Defaults to `-6`.
* <b>`max`</b>: An optional `float`. Defaults to `6`.
* <b>`num_bits`</b>: An optional `int`. Defaults to `8`.
* <b>`narrow_range`</b>: An optional `bool`. Defaults to `False`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `float32`.
Backpropagated gradients below the FakeQuantWithMinMaxArgs operation:
`gradients * (inputs >= min && inputs <= max)`.