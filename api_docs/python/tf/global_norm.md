<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.global_norm" />
</div>

# tf.global_norm

``` python
global_norm(
    t_list,
    name=None
)
```



Defined in [`tensorflow/python/ops/clip_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/clip_ops.py).

See the guide: [Training > Gradient Clipping](../../../api_guides/python/train.md#Gradient_Clipping)

Computes the global norm of multiple tensors.

Given a tuple or list of tensors `t_list`, this operation returns the
global norm of the elements in all tensors in `t_list`. The global norm is
computed as:

`global_norm = sqrt(sum([l2norm(t)**2 for t in t_list]))`

Any entries in `t_list` that are of type None are ignored.

#### Args:

* <b>`t_list`</b>: A tuple or list of mixed `Tensors`, `IndexedSlices`, or None.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A 0-D (scalar) `Tensor` of type `float`.


#### Raises:

* <b>`TypeError`</b>: If `t_list` is not a sequence.