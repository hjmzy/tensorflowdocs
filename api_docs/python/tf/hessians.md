<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.hessians" />
</div>

# tf.hessians

``` python
hessians(
    ys,
    xs,
    name='hessians',
    colocate_gradients_with_ops=False,
    gate_gradients=False,
    aggregation_method=None
)
```



Defined in [`tensorflow/python/ops/gradients_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/gradients_impl.py).

See the guide: [Training > Gradient Computation](../../../api_guides/python/train.md#Gradient_Computation)

Constructs the Hessian of sum of `ys` with respect to `x` in `xs`.

`hessians()` adds ops to the graph to output the Hessian matrix of `ys`
with respect to `xs`.  It returns a list of `Tensor` of length `len(xs)`
where each tensor is the Hessian of `sum(ys)`. This function currently
only supports evaluating the Hessian with respect to (a list of) one-
dimensional tensors.

The Hessian is a matrix of second-order partial derivatives of a scalar
tensor (see https://en.wikipedia.org/wiki/Hessian_matrix for more details).

#### Args:

* <b>`ys`</b>: A `Tensor` or list of tensors to be differentiated.
* <b>`xs`</b>: A `Tensor` or list of tensors to be used for differentiation.
* <b>`name`</b>: Optional name to use for grouping all the gradient ops together.
    defaults to 'hessians'.
* <b>`colocate_gradients_with_ops`</b>: See `gradients()` documentation for details.
* <b>`gate_gradients`</b>: See `gradients()` documentation for details.
* <b>`aggregation_method`</b>: See `gradients()` documentation for details.


#### Returns:

A list of Hessian matrices of `sum(ys)` for each `x` in `xs`.


#### Raises:

* <b>`LookupError`</b>: if one of the operations between `xs` and `ys` does not
    have a registered gradient function.