<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ones_initializer" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.ones_initializer

## Class `ones_initializer`

Inherits From: [`Initializer`](../tf/keras/initializers/Initializer.md)

### Aliases:

* Class `tf.initializers.ones`
* Class `tf.keras.initializers.Ones`
* Class `tf.ones_initializer`



Defined in [`tensorflow/python/ops/init_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/init_ops.py).

See the guide: [Variables > Sharing Variables](../../../api_guides/python/state_ops.md#Sharing_Variables)

Initializer that generates tensors initialized to 1.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(dtype=tf.float32)
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





