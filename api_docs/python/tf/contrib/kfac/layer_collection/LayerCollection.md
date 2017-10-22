<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.layer_collection.LayerCollection" />
<meta itemprop="property" content="generic_registrations"/>
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="losses"/>
<meta itemprop="property" content="subgraph"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="create_subgraph"/>
<meta itemprop="property" content="get_blocks"/>
<meta itemprop="property" content="get_factors"/>
<meta itemprop="property" content="get_use_count_map"/>
<meta itemprop="property" content="make_or_get_factor"/>
<meta itemprop="property" content="register_block"/>
<meta itemprop="property" content="register_categorical_predictive_distribution"/>
<meta itemprop="property" content="register_conv2d"/>
<meta itemprop="property" content="register_fully_connected"/>
<meta itemprop="property" content="register_generic"/>
<meta itemprop="property" content="register_multi_bernoulli_predictive_distribution"/>
<meta itemprop="property" content="register_normal_predictive_distribution"/>
<meta itemprop="property" content="total_loss"/>
<meta itemprop="property" content="total_sampled_loss"/>
</div>

# tf.contrib.kfac.layer_collection.LayerCollection

## Class `LayerCollection`





Defined in [`tensorflow/contrib/kfac/python/ops/layer_collection.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/layer_collection.py).

Registry of information about layers and losses.

Note that you need to create a new one of these for each MatrixEstimator or
KfacOptimizer.

#### Attributes:

* <b>`fisher_blocks`</b>: a LayersParamsDict (subclass of OrderedDict) mapping layer
      parameters (Tensors or tuples of Tensors) to FisherBlock instances.
* <b>`fisher_factors`</b>: an OrderedDict mapping tuples to FisherFactor instances.
* <b>`generic_registrations`</b>: a list of variables registered via a generic layer
      registration. Generic registrations handle any and all of the ways a
      variable is used in the graph, which means we don't need to check
      their registration when verifying the correctness of the graph.
* <b>`losses`</b>: a list of LossFunction objects. The loss to be optimized is their
      sum.

## Properties

<h3 id="generic_registrations"><code>generic_registrations</code></h3>



<h3 id="graph"><code>graph</code></h3>



<h3 id="losses"><code>losses</code></h3>

LossFunctions registered with this LayerCollection.

<h3 id="subgraph"><code>subgraph</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    graph=None,
    name='LayerCollection'
)
```



<h3 id="create_subgraph"><code>create_subgraph</code></h3>

``` python
create_subgraph()
```



<h3 id="get_blocks"><code>get_blocks</code></h3>

``` python
get_blocks()
```



<h3 id="get_factors"><code>get_factors</code></h3>

``` python
get_factors()
```



<h3 id="get_use_count_map"><code>get_use_count_map</code></h3>

``` python
get_use_count_map()
```

Returns a dict of variables to their number of registrations.

<h3 id="make_or_get_factor"><code>make_or_get_factor</code></h3>

``` python
make_or_get_factor(
    cls,
    args
)
```



<h3 id="register_block"><code>register_block</code></h3>

``` python
register_block(
    layer_key,
    fisher_block
)
```

Validates and registers the layer_key associated with the fisher_block.

Validation consists of checking whether the key was already registered or
if any of the elements of layer_key (if it's a tuple) were already
registered as part of another tuple (throws an error if so). If any of the
elements were registered by themselves, or as part of tuples that are
subsets of this layer_key, those registrations are first removed.

If the layer_key is a subset of an existing registration, registration of
the new, smaller layer_key is skipped.

e.g. If registrations include {'a': foo, ('b', 'c'): bar}, then
  - register_layer('a', baz) -> ValueError
  - register_layer(('b', 'c', 'd'), baz) ->
    {'a': foo, ('b', 'c', 'd'): baz}
  - register_layer('b', baz) ->
    {'a': foo, ('b', 'c'): bar} (No change)
  - register_layer(('a', 'd'), baz) ->
    {('a', 'd'): baz, ('b', 'c'): bar}
  - register_layer(('b', 'd'), baz) -> ValueError

#### Args:

* <b>`layer_key`</b>: The key to check for in existing registrations and to register
      if valid.
* <b>`fisher_block`</b>: The associated fisher block.


#### Raises:

* <b>`ValueError`</b>: If the layer_key was already registered, or if a subset of the
      layer_key has already been registered as part of a different tuple.

<h3 id="register_categorical_predictive_distribution"><code>register_categorical_predictive_distribution</code></h3>

``` python
register_categorical_predictive_distribution(
    logits,
    seed=None,
    targets=None,
    name=None
)
```

Registers a categorical predictive distribution.

#### Args:

* <b>`logits`</b>: The logits of the distribution (i.e. its parameters).
* <b>`seed`</b>: The seed for the RNG (for debugging) (Default: None)
* <b>`targets`</b>: (OPTIONAL) The targets for the loss function.  Only required if
    one wants to call total_loss() instead of total_sampled_loss().
    total_loss() is required, for example, to estimate the
    "empirical Fisher" (instead of the true Fisher).
    (Default: None)
* <b>`name`</b>: (OPTIONAL) str or None. Unique name for this loss function. If None,
    a new name is generated. (Default: None)

<h3 id="register_conv2d"><code>register_conv2d</code></h3>

``` python
register_conv2d(
    params,
    strides,
    padding,
    inputs,
    outputs,
    approx=APPROX_KRONECKER_NAME
)
```



<h3 id="register_fully_connected"><code>register_fully_connected</code></h3>

``` python
register_fully_connected(
    params,
    inputs,
    outputs,
    approx=APPROX_KRONECKER_NAME
)
```



<h3 id="register_generic"><code>register_generic</code></h3>

``` python
register_generic(
    params,
    batch_size,
    approx=APPROX_DIAGONAL_NAME
)
```



<h3 id="register_multi_bernoulli_predictive_distribution"><code>register_multi_bernoulli_predictive_distribution</code></h3>

``` python
register_multi_bernoulli_predictive_distribution(
    logits,
    seed=None,
    targets=None,
    name=None
)
```

Registers a multi-Bernoulli predictive distribution.

#### Args:

* <b>`logits`</b>: The logits of the distribution (i.e. its parameters).
* <b>`seed`</b>: The seed for the RNG (for debugging) (Default: None)
* <b>`targets`</b>: (OPTIONAL) The targets for the loss function.  Only required if
    one wants to call total_loss() instead of total_sampled_loss().
    total_loss() is required, for example, to estimate the
    "empirical Fisher" (instead of the true Fisher).
    (Default: None)
* <b>`name`</b>: (OPTIONAL) str or None. Unique name for this loss function. If None,
    a new name is generated. (Default: None)

<h3 id="register_normal_predictive_distribution"><code>register_normal_predictive_distribution</code></h3>

``` python
register_normal_predictive_distribution(
    mean,
    var=0.5,
    seed=None,
    targets=None,
    name=None
)
```

Registers a normal predictive distribution.

#### Args:

* <b>`mean`</b>: The mean vector defining the distribution.
* <b>`var`</b>: The variance (must be a scalar).  Note that the default value of
    0.5 corresponds to a standard squared error loss (target -
    prediction)**2. If your squared error loss is of the form
    0.5*(target - prediction)**2 you should use var=1.0. (Default: 0.5)
* <b>`seed`</b>: The seed for the RNG (for debugging) (Default: None)
* <b>`targets`</b>: (OPTIONAL) The targets for the loss function.  Only required if
    one wants to call total_loss() instead of total_sampled_loss().
    total_loss() is required, for example, to estimate the
    "empirical Fisher" (instead of the true Fisher).
    (Default: None)
* <b>`name`</b>: (OPTIONAL) str or None. Unique name for this loss function. If None,
    a new name is generated. (Default: None)

<h3 id="total_loss"><code>total_loss</code></h3>

``` python
total_loss()
```



<h3 id="total_sampled_loss"><code>total_sampled_loss</code></h3>

``` python
total_sampled_loss()
```





