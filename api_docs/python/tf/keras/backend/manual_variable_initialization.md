<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.manual_variable_initialization" />
</div>

# tf.keras.backend.manual_variable_initialization

``` python
manual_variable_initialization(value)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Sets the manual variable initialization flag.

This boolean flag determines whether
variables should be initialized
as they are instantiated (default), or if
the user should handle the initialization
(e.g. via `tf.initialize_all_variables()`).

#### Arguments:

* <b>`value`</b>: Python boolean.