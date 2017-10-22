<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.hard_sigmoid" />
</div>

# tf.keras.backend.hard_sigmoid

``` python
hard_sigmoid(x)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Segment-wise linear approximation of sigmoid.

Faster than sigmoid.
Returns `0.` if `x < -2.5`, `1.` if `x > 2.5`.
In `-2.5 <= x <= 2.5`, returns `0.2 * x + 0.5`.

#### Arguments:

* <b>`x`</b>: A tensor or variable.


#### Returns:

A tensor.