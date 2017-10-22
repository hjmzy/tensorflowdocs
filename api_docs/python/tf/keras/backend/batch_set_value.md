<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.batch_set_value" />
</div>

# tf.keras.backend.batch_set_value

``` python
batch_set_value(tuples)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Sets the values of many tensor variables at once.

#### Arguments:

* <b>`tuples`</b>: a list of tuples `(tensor, value)`.
        `value` should be a Numpy array.