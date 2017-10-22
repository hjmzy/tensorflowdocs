<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.GANTrainOps" />
<meta itemprop="property" content="discriminator_train_op"/>
<meta itemprop="property" content="generator_train_op"/>
<meta itemprop="property" content="global_step_inc_op"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.contrib.gan.GANTrainOps

## Class `GANTrainOps`





Defined in [`tensorflow/contrib/gan/python/namedtuples.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/namedtuples.py).

GANTrainOps contains the training ops.

#### Args:

* <b>`generator_train_op`</b>: Op that performs a generator update step.
* <b>`discriminator_train_op`</b>: Op that performs a discriminator update step.
* <b>`global_step_inc_op`</b>: Op that increments the shared global step.

## Properties

<h3 id="discriminator_train_op"><code>discriminator_train_op</code></h3>

Alias for field number 1

<h3 id="generator_train_op"><code>generator_train_op</code></h3>

Alias for field number 0

<h3 id="global_step_inc_op"><code>global_step_inc_op</code></h3>

Alias for field number 2



## Methods

<h3 id="__new__"><code>__new__</code></h3>

``` python
__new__(
    _cls,
    generator_train_op,
    discriminator_train_op,
    global_step_inc_op
)
```

Create new instance of GANTrainOps(generator_train_op, discriminator_train_op, global_step_inc_op)



