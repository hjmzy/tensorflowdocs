<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.nccl.all_prod" />
</div>

# tf.contrib.nccl.all_prod

``` python
all_prod(tensors)
```



Defined in [`tensorflow/contrib/nccl/python/ops/nccl_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/nccl/python/ops/nccl_ops.py).

Returns a list of tensors with the all-reduce product across `tensors`.

The computation is done with an all-reduce operation, so if only some of the
returned tensors are evaluated then the computation will hang.

#### Args:

* <b>`tensors`</b>: The input tensors across which to multiply; must be assigned
    to GPU devices.


#### Returns:

List of tensors, each with the product of the input tensors, where tensor i
has the same device as `tensors[i]`.