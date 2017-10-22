<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.lecun_uniform" />
</div>

# tf.keras.initializers.lecun_uniform

``` python
lecun_uniform(seed=None)
```



Defined in [`tensorflow/python/keras/_impl/keras/initializers.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/initializers.py).

LeCun uniform initializer.

It draws samples from a uniform distribution within [-limit, limit]
where `limit` is `sqrt(3 / fan_in)`
where `fan_in` is the number of input units in the weight tensor.

#### Arguments:

* <b>`seed`</b>: A Python integer. Used to seed the random generator.


#### Returns:

    An initializer.

References:
    LeCun 98, Efficient Backprop,
    http://yann.lecun.com/exdb/publis/pdf/lecun-98b.pdf