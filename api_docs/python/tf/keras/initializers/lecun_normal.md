<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.initializers.lecun_normal" />
</div>

# tf.keras.initializers.lecun_normal

``` python
lecun_normal(seed=None)
```



Defined in [`tensorflow/python/keras/_impl/keras/initializers.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/initializers.py).

LeCun normal initializer.

It draws samples from a truncated normal distribution centered on 0
with `stddev = sqrt(1 / fan_in)`
where `fan_in` is the number of input units in the weight tensor.

#### Arguments:

* <b>`seed`</b>: A Python integer. Used to seed the random generator.


#### Returns:

    An initializer.

References:
    - [Self-Normalizing Neural Networks](https://arxiv.org/abs/1706.02515)
    - [Efficient
    Backprop](http://yann.lecun.com/exdb/publis/pdf/lecun-98b.pdf)