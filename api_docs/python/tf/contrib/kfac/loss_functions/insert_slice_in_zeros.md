<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.loss_functions.insert_slice_in_zeros" />
</div>

# tf.contrib.kfac.loss_functions.insert_slice_in_zeros

``` python
insert_slice_in_zeros(
    slice_to_insert,
    dim,
    dim_size,
    position
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/loss_functions.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/loss_functions.py).

Inserts slice into a larger tensors of zeros.

Forms a new tensor that which is the same shape as slice_, except that
the dimension given by 'dim' is expanded to the size given by 'dim_size'.
'position' determines the position (index) of the slice in that dimension.

Assumes slice_to_insert.shape[dim] = 1.

#### Args:

* <b>`slice_to_insert`</b>: The slice to insert.
* <b>`dim`</b>: The dimension which to expand with zeros.
* <b>`dim_size`</b>: The new size of the 'dim' dimension.
* <b>`position`</b>: The position of 'slice_' in the new tensor.


#### Returns:

The new tensor.


#### Raises:

* <b>`ValueError`</b>: If the slice's shape at the given dim is not 1.