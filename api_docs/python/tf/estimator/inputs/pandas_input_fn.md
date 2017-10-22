<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.inputs.pandas_input_fn" />
</div>

# tf.estimator.inputs.pandas_input_fn

``` python
pandas_input_fn(
    x,
    y=None,
    batch_size=128,
    num_epochs=1,
    shuffle=None,
    queue_capacity=1000,
    num_threads=1,
    target_column='target'
)
```



Defined in [`tensorflow/python/estimator/inputs/pandas_io.py`](https://www.tensorflow.org/code/tensorflow/python/estimator/inputs/pandas_io.py).

Returns input function that would feed Pandas DataFrame into the model.

Note: `y`'s index must match `x`'s index.

#### Args:

* <b>`x`</b>: pandas `DataFrame` object.
* <b>`y`</b>: pandas `Series` object. `None` if absent.
* <b>`batch_size`</b>: int, size of batches to return.
* <b>`num_epochs`</b>: int, number of epochs to iterate over data. If not `None`,
    read attempts that would exceed this value will raise `OutOfRangeError`.
* <b>`shuffle`</b>: bool, whether to read the records in random order.
* <b>`queue_capacity`</b>: int, size of the read queue. If `None`, it will be set
    roughly to the size of `x`.
* <b>`num_threads`</b>: Integer, number of threads used for reading and enqueueing. In
    order to have predicted and repeatable order of reading and enqueueing,
    such as in prediction and evaluation mode, `num_threads` should be 1.
* <b>`target_column`</b>: str, name to give the target column `y`.


#### Returns:

Function, that has signature of ()->(dict of `features`, `target`)


#### Raises:

* <b>`ValueError`</b>: if `x` already contains a column with the same name as `y`, or
    if the indexes of `x` and `y` don't match.
* <b>`TypeError`</b>: `shuffle` is not bool.