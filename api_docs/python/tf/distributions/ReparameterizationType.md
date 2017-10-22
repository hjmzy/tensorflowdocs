<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distributions.ReparameterizationType" />
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.distributions.ReparameterizationType

## Class `ReparameterizationType`



### Aliases:

* Class `tf.contrib.distributions.ReparameterizationType`
* Class `tf.distributions.ReparameterizationType`



Defined in [`tensorflow/python/ops/distributions/distribution.py`](https://www.tensorflow.org/code/tensorflow/python/ops/distributions/distribution.py).

See the guide: [Statistical Distributions (contrib) > Base classes](../../../../api_guides/python/contrib.distributions.md#Base_classes)

Instances of this class represent how sampling is reparameterized.

Two static instances exist in the distributions library, signifying
one of two possible properties for samples from a distribution:

`FULLY_REPARAMETERIZED`: Samples from the distribution are fully
  reparameterized, and straight-through gradients are supported.

`NOT_REPARAMETERIZED`: Samples from the distribution are not fully
  reparameterized, and straight-through gradients are either partially
  unsupported or are not supported at all. In this case, for purposes of
  e.g. RL or variational inference, it is generally safest to wrap the
  sample results in a `stop_gradients` call and instead use policy
  gradients / surrogate loss instead.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(rep_type)
```



<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```

Determine if this `ReparameterizationType` is equal to another.

Since RepaparameterizationType instances are constant static global
instances, equality checks if two instances' id() values are equal.

#### Args:

* <b>`other`</b>: Object to compare against.


#### Returns:

`self is other`.



