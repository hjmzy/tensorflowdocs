<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.bayesflow.stochastic_tensor.ObservedStochasticTensor" />
<meta itemprop="property" content="distribution"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="value_type"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="entropy"/>
<meta itemprop="property" content="loss"/>
<meta itemprop="property" content="mean"/>
<meta itemprop="property" content="value"/>
</div>

# tf.contrib.bayesflow.stochastic_tensor.ObservedStochasticTensor

## Class `ObservedStochasticTensor`

Inherits From: [`StochasticTensor`](../../../../tf/contrib/bayesflow/stochastic_tensor/StochasticTensor.md)



Defined in [`tensorflow/contrib/bayesflow/python/ops/stochastic_tensor_impl.py`](https://www.tensorflow.org/code/tensorflow/contrib/bayesflow/python/ops/stochastic_tensor_impl.py).

A StochasticTensor with an observed value.

## Properties

<h3 id="distribution"><code>distribution</code></h3>



<h3 id="dtype"><code>dtype</code></h3>



<h3 id="graph"><code>graph</code></h3>



<h3 id="name"><code>name</code></h3>



<h3 id="value_type"><code>value_type</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    dist,
    value,
    name=None
)
```

Construct an `ObservedStochasticTensor`.

`ObservedStochasticTensor` is backed by distribution `dist` and uses the
provided value instead of using the current value type to draw a value from
the distribution. The provided value argument must be appropriately shaped
to have come from the distribution.

#### Args:

* <b>`dist`</b>: an instance of `Distribution`.
* <b>`value`</b>: a Tensor containing the observed value
* <b>`name`</b>: a name for this `ObservedStochasticTensor` and its ops.


#### Raises:

* <b>`TypeError`</b>: if `dist` is not an instance of `Distribution`.
* <b>`ValueError`</b>: if `value` is not compatible with the distribution.

<h3 id="entropy"><code>entropy</code></h3>

``` python
entropy(name='entropy')
```



<h3 id="loss"><code>loss</code></h3>

``` python
loss(
    final_loss,
    name=None
)
```



<h3 id="mean"><code>mean</code></h3>

``` python
mean(name='mean')
```



<h3 id="value"><code>value</code></h3>

``` python
value(name='value')
```





