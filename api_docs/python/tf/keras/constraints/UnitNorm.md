<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.constraints.UnitNorm" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.constraints.UnitNorm

## Class `UnitNorm`

Inherits From: [`Constraint`](../../../tf/keras/constraints/Constraint.md)

### Aliases:

* Class `tf.keras.constraints.UnitNorm`
* Class `tf.keras.constraints.unit_norm`



Defined in [`tensorflow/python/keras/_impl/keras/constraints.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/constraints.py).

Constrains the weights incident to each hidden unit to have unit norm.

#### Arguments:

* <b>`axis`</b>: integer, axis along which to calculate weight norms.
        For instance, in a `Dense` layer the weight matrix
        has shape `(input_dim, output_dim)`,
        set `axis` to `0` to constrain each weight vector
        of length `(input_dim,)`.
        In a `Conv2D` layer with `data_format="channels_last"`,
        the weight tensor has shape
        `(rows, cols, input_depth, output_depth)`,
        set `axis` to `[0, 1, 2]`
        to constrain the weights of each filter tensor of size
        `(rows, cols, input_depth)`.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(axis=0)
```



<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(w)
```



<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```





