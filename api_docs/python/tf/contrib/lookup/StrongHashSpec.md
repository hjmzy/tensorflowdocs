<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.lookup.StrongHashSpec" />
<meta itemprop="property" content="hasher"/>
<meta itemprop="property" content="key"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.contrib.lookup.StrongHashSpec

## Class `StrongHashSpec`

Inherits From: [`HasherSpec`](../../../tf/contrib/lookup/HasherSpec.md)



Defined in [`tensorflow/python/ops/lookup_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/lookup_ops.py).

A structure to specify a key of the strong keyed hash spec.

The strong hash requires a `key`, which is a list of 2 unsigned integer
numbers. These should be non-zero; random numbers generated from random.org
would be a fine choice.

#### Fields:

* <b>`key`</b>: The key to be used by the keyed hashing function.

## Properties

<h3 id="hasher"><code>hasher</code></h3>

Alias for field number 0

<h3 id="key"><code>key</code></h3>

Alias for field number 1



## Methods

<h3 id="__new__"><code>__new__</code></h3>

``` python
@staticmethod
__new__(
    cls,
    key
)
```





