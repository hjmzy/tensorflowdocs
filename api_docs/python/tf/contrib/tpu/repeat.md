<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.repeat" />
</div>

# tf.contrib.tpu.repeat

``` python
repeat(
    n,
    body,
    inputs=None,
    infeed_queue=None,
    name=None
)
```



Defined in [`tensorflow/contrib/tpu/python/tpu/training_loop.py`](https://www.tensorflow.org/code/tensorflow/contrib/tpu/python/tpu/training_loop.py).

Builds a training loop that executes a fixed number of interations.

The set of loop-carried tensors correspond to `inputs`.
`body` must be a function that takes and returns the values of the
loop-carried tensors.

#### Args:

* <b>`n`</b>: the number of loop iterations
* <b>`body`</b>: a Python function that builds the loop body.
* <b>`inputs`</b>: a list of initial values passed into the training loop or
    None (equivalent to an empty list).
* <b>`infeed_queue`</b>: if not None, the infeed queue from which to append a tuple
    of arguments as inputs to condition.
* <b>`name`</b>: an optional name for the loop.

#### Returns:

The final values of the loop-carried tensors.

#### Raises:

* <b>`ValueError`</b>: if there is a type error.