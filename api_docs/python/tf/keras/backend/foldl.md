<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.foldl" />
</div>

# tf.keras.backend.foldl

``` python
foldl(
    fn,
    elems,
    initializer=None,
    name=None
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Reduce elems using fn to combine them from left to right.

#### Arguments:

* <b>`fn`</b>: Callable that will be called upon each element in elems and an
        accumulator, for instance `lambda acc, x: acc + x`
* <b>`elems`</b>: tensor
* <b>`initializer`</b>: The first value used (`elems[0]` in case of None)
* <b>`name`</b>: A string name for the foldl node in the graph


#### Returns:

Tensor with same type and shape as `initializer`.