<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.rint" />
</div>

# tf.rint

``` python
rint(
    x,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_math_ops.py`.

See the guide: [Math > Basic Math Functions](../../../api_guides/python/math_ops.md#Basic_Math_Functions)

Returns element-wise integer closest to x.

If the result is midway between two representable values,
the even representable is chosen.
For example:

```
rint(-1.5) ==> -2.0
rint(0.5000001) ==> 1.0
rint([-1.7, -1.5, -0.2, 0.2, 1.5, 1.7, 2.0]) ==> [-2., -2., -0., 0., 2., 2., 2.]
```

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.