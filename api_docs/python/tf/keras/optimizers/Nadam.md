<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.optimizers.Nadam" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
<meta itemprop="property" content="get_gradients"/>
<meta itemprop="property" content="get_updates"/>
<meta itemprop="property" content="get_weights"/>
<meta itemprop="property" content="set_weights"/>
</div>

# tf.keras.optimizers.Nadam

## Class `Nadam`

Inherits From: [`Optimizer`](../../../tf/keras/optimizers/Optimizer.md)



Defined in [`tensorflow/python/keras/_impl/keras/optimizers.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/optimizers.py).

Nesterov Adam optimizer.

Much like Adam is essentially RMSprop with momentum,
Nadam is Adam RMSprop with Nesterov momentum.

Default parameters follow those provided in the paper.
It is recommended to leave the parameters of this optimizer
at their default values.

#### Arguments:

* <b>`lr`</b>: float >= 0. Learning rate.
    beta_1/beta_2: floats, 0 < beta < 1. Generally close to 1.
* <b>`epsilon`</b>: float >= 0. Fuzz factor.

References:
    - [Nadam report](http://cs229.stanford.edu/proj2015/054_report.pdf)
    - [On the importance of initialization and momentum in deep
      learning](http://www.cs.toronto.edu/~fritz/absps/momentum.pdf)

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    lr=0.002,
    beta_1=0.9,
    beta_2=0.999,
    epsilon=1e-08,
    schedule_decay=0.004,
    **kwargs
)
```



<h3 id="from_config"><code>from_config</code></h3>

``` python
from_config(
    cls,
    config
)
```



<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```



<h3 id="get_gradients"><code>get_gradients</code></h3>

``` python
get_gradients(
    loss,
    params
)
```



<h3 id="get_updates"><code>get_updates</code></h3>

``` python
get_updates(
    loss,
    params
)
```



<h3 id="get_weights"><code>get_weights</code></h3>

``` python
get_weights()
```

Returns the current value of the weights of the optimizer.

#### Returns:

A list of numpy arrays.

<h3 id="set_weights"><code>set_weights</code></h3>

``` python
set_weights(weights)
```

Sets the weights of the optimizer, from Numpy arrays.

Should only be called after computing the gradients
(otherwise the optimizer has no weights).

#### Arguments:

* <b>`weights`</b>: a list of Numpy arrays. The number
        of arrays and their shape must match
        number of the dimensions of the weights
        of the optimizer (i.e. it should match the
        output of `get_weights`).


#### Raises:

* <b>`ValueError`</b>: in case of incompatible weight shapes.



