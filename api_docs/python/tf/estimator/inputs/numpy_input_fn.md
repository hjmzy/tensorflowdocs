<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.inputs.numpy_input_fn" />
</div>

# tf.estimator.inputs.numpy_input_fn

``` python
numpy_input_fn(
    x,
    y=None,
    batch_size=128,
    num_epochs=1,
    shuffle=None,
    queue_capacity=1000,
    num_threads=1
)
```



Defined in [`tensorflow/python/estimator/inputs/numpy_io.py`](https://www.tensorflow.org/code/tensorflow/python/estimator/inputs/numpy_io.py).

Returns input function that would feed dict of numpy arrays into the model.

This returns a function outputting `features` and `target` based on the dict
of numpy arrays. The dict `features` has the same keys as the `x`.

Example:

```python
age = np.arange(4) * 1.0
height = np.arange(32, 36)
x = {'age': age, 'height': height}
y = np.arange(-32, -28)

with tf.Session() as session:
  input_fn = numpy_io.numpy_input_fn(
      x, y, batch_size=2, shuffle=False, num_epochs=1)
```

#### Args:

* <b>`x`</b>: dict of numpy array object.
* <b>`y`</b>: numpy array object. `None` if absent.
* <b>`batch_size`</b>: Integer, size of batches to return.
* <b>`num_epochs`</b>: Integer, number of epochs to iterate over data. If `None` will
    run forever.
* <b>`shuffle`</b>: Boolean, if True shuffles the queue. Avoid shuffle at prediction
    time.
* <b>`queue_capacity`</b>: Integer, size of queue to accumulate.
* <b>`num_threads`</b>: Integer, number of threads used for reading and enqueueing. In
    order to have predicted and repeatable order of reading and enqueueing,
    such as in prediction and evaluation mode, `num_threads` should be 1.


#### Returns:

Function, that has signature of ()->(dict of `features`, `target`)


#### Raises:

* <b>`ValueError`</b>: if the shape of `y` mismatches the shape of values in `x` (i.e.,
    values in `x` have same shape).
* <b>`TypeError`</b>: `x` is not a dict or `shuffle` is not bool.