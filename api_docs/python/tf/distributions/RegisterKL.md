<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distributions.RegisterKL" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.distributions.RegisterKL

## Class `RegisterKL`



### Aliases:

* Class `tf.contrib.distributions.RegisterKL`
* Class `tf.distributions.RegisterKL`



Defined in [`tensorflow/python/ops/distributions/kullback_leibler.py`](https://www.tensorflow.org/code/tensorflow/python/ops/distributions/kullback_leibler.py).

See the guide: [Statistical Distributions (contrib) > Kullback-Leibler Divergence](../../../../api_guides/python/contrib.distributions.md#Kullback_Leibler_Divergence)

Decorator to register a KL divergence implementation function.

Usage:

@distributions.RegisterKL(distributions.Normal, distributions.Normal)
def _kl_normal_mvn(norm_a, norm_b):
  # Return KL(norm_a || norm_b)

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    dist_cls_a,
    dist_cls_b
)
```

Initialize the KL registrar.

#### Args:

* <b>`dist_cls_a`</b>: the class of the first argument of the KL divergence.
* <b>`dist_cls_b`</b>: the class of the second argument of the KL divergence.

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(kl_fn)
```

Perform the KL registration.

#### Args:

* <b>`kl_fn`</b>: The function to use for the KL divergence.


#### Returns:

kl_fn


#### Raises:

* <b>`TypeError`</b>: if kl_fn is not a callable.
* <b>`ValueError`</b>: if a KL divergence function has already been registered for
    the given argument classes.



