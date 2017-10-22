<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.range_input_producer" />
</div>

# tf.train.range_input_producer

``` python
range_input_producer(
    limit,
    num_epochs=None,
    shuffle=True,
    seed=None,
    capacity=32,
    shared_name=None,
    name=None
)
```



Defined in [`tensorflow/python/training/input.py`](https://www.tensorflow.org/code/tensorflow/python/training/input.py).

See the guide: [Inputs and Readers > Input pipeline](../../../../api_guides/python/io_ops.md#Input_pipeline)

Produces the integers from 0 to limit-1 in a queue.

Note: if `num_epochs` is not `None`, this function creates local counter
`epochs`. Use `local_variables_initializer()` to initialize local variables.

#### Args:

* <b>`limit`</b>: An int32 scalar tensor.
* <b>`num_epochs`</b>: An integer (optional). If specified, `range_input_producer`
    produces each integer `num_epochs` times before generating an
    OutOfRange error. If not specified, `range_input_producer` can cycle
    through the integers an unlimited number of times.
* <b>`shuffle`</b>: Boolean. If true, the integers are randomly shuffled within each
    epoch.
* <b>`seed`</b>: An integer (optional). Seed used if shuffle == True.
* <b>`capacity`</b>: An integer. Sets the queue capacity.
* <b>`shared_name`</b>: (optional). If set, this queue will be shared under the given
    name across multiple sessions.
* <b>`name`</b>: A name for the operations (optional).


#### Returns:

A Queue with the output integers.  A `QueueRunner` for the Queue
is added to the current `Graph`'s `QUEUE_RUNNER` collection.