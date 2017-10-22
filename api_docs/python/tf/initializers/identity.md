<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initializers.identity" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.initializers.identity

## Class `identity`

Inherits From: [`Initializer`](../../tf/keras/initializers/Initializer.md)

### Aliases:

* Class `tf.initializers.identity`
* Class `tf.keras.initializers.Identity`



Defined in [`tensorflow/python/ops/init_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/init_ops.py).

Initializer that generates the identity matrix.

Only use for 2D matrices.

#### Args:

* <b>`gain`</b>: Multiplicative factor to apply to the identity matrix.
* <b>`dtype`</b>: The type of the output.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    gain=1.0,
    dtype=tf.float32
)
```



<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    shape,
    dtype=None,
    partition_info=None
)
```



<h3 id="from_config"><code>from_config</code></h3>

``` python
from_config(
    cls,
    config
)
```

Instantiates an initializer from a configuration dictionary.

Example:

```python
initializer = RandomUniform(-1, 1)
config = initializer.get_config()
initializer = RandomUniform.from_config(config)
```

#### Args:

* <b>`config`</b>: A Python dictionary.
    It will typically be the output of `get_config`.


#### Returns:

An Initializer instance.

<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```





