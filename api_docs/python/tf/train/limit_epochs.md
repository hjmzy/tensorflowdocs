<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.limit_epochs" />
</div>

# tf.train.limit_epochs

``` python
limit_epochs(
    tensor,
    num_epochs=None,
    name=None
)
```



Defined in [`tensorflow/python/training/input.py`](https://www.tensorflow.org/code/tensorflow/python/training/input.py).

See the guide: [Inputs and Readers > Input pipeline](../../../../api_guides/python/io_ops.md#Input_pipeline)

Returns tensor `num_epochs` times and then raises an `OutOfRange` error.

Note: creates local counter `epochs`. Use `local_variables_initializer()` to
initialize local variables.

#### Args:

* <b>`tensor`</b>: Any `Tensor`.
* <b>`num_epochs`</b>: A positive integer (optional).  If specified, limits the number
    of steps the output tensor may be evaluated.
* <b>`name`</b>: A name for the operations (optional).


#### Returns:

tensor or `OutOfRange`.


#### Raises:

* <b>`ValueError`</b>: if `num_epochs` is invalid.