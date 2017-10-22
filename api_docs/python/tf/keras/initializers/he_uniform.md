<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.he_uniform" />
</div>

# tf.keras.initializers.he_uniform

``` python
he_uniform(seed=None)
```



Defined in [`tensorflow/python/keras/_impl/keras/initializers.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/initializers.py).

He uniform variance scaling initializer.

It draws samples from a uniform distribution within [-limit, limit]
where `limit` is `sqrt(6 / fan_in)`
where `fan_in` is the number of input units in the weight tensor.

#### Arguments:

* <b>`seed`</b>: A Python integer. Used to seed the random generator.


#### Returns:

    An initializer.

References:
    He et al., http://arxiv.org/abs/1502.01852