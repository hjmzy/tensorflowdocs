<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.repeat_elements" />
</div>

# tf.keras.backend.repeat_elements

``` python
repeat_elements(
    x,
    rep,
    axis
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Repeats the elements of a tensor along an axis, like `np.repeat`.

If `x` has shape `(s1, s2, s3)` and `axis` is `1`, the output
will have shape `(s1, s2 * rep, s3)`.

#### Arguments:

* <b>`x`</b>: Tensor or variable.
* <b>`rep`</b>: Python integer, number of times to repeat.
* <b>`axis`</b>: Axis along which to repeat.


#### Returns:

A tensor.