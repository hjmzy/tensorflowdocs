<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.GANLoss" />
<meta itemprop="property" content="discriminator_loss"/>
<meta itemprop="property" content="generator_loss"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.contrib.gan.GANLoss

## Class `GANLoss`





Defined in [`tensorflow/contrib/gan/python/namedtuples.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/namedtuples.py).

GANLoss contains the generator and discriminator losses.

#### Args:

* <b>`generator_loss`</b>: A tensor for the generator loss.
* <b>`discriminator_loss`</b>: A tensor for the discriminator loss.

## Properties

<h3 id="discriminator_loss"><code>discriminator_loss</code></h3>

Alias for field number 1

<h3 id="generator_loss"><code>generator_loss</code></h3>

Alias for field number 0



## Methods

<h3 id="__new__"><code>__new__</code></h3>

``` python
__new__(
    _cls,
    generator_loss,
    discriminator_loss
)
```

Create new instance of GANLoss(generator_loss, discriminator_loss)



