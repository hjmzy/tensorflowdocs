<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.factorization.GmmAlgorithm" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="alphas"/>
<meta itemprop="property" content="assignments"/>
<meta itemprop="property" content="clusters"/>
<meta itemprop="property" content="covariances"/>
<meta itemprop="property" content="init_ops"/>
<meta itemprop="property" content="is_initialized"/>
<meta itemprop="property" content="scores"/>
<meta itemprop="property" content="training_ops"/>
<meta itemprop="property" content="CLUSTERS_COVS_VARIABLE"/>
<meta itemprop="property" content="CLUSTERS_VARIABLE"/>
<meta itemprop="property" content="CLUSTERS_WEIGHT"/>
</div>

# tf.contrib.factorization.GmmAlgorithm

## Class `GmmAlgorithm`





Defined in [`tensorflow/contrib/factorization/python/ops/gmm_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/factorization/python/ops/gmm_ops.py).

Tensorflow Gaussian mixture model clustering class.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    data,
    num_classes,
    initial_means=None,
    params='wmc',
    covariance_type=FULL_COVARIANCE,
    random_seed=0
)
```

Constructor.

#### Args:

* <b>`data`</b>: a list of Tensors with data, each row is a new example.
* <b>`num_classes`</b>: number of clusters.
* <b>`initial_means`</b>: a Tensor with a matrix of means. If None, means are
    computed by sampling randomly.
* <b>`params`</b>: Controls which parameters are updated in the training
    process. Can contain any combination of "w" for weights, "m" for
    means, and "c" for covariances.
* <b>`covariance_type`</b>: one of "full", "diag".
* <b>`random_seed`</b>: Seed for PRNG used to initialize seeds.


#### Raises:

Exception if covariance type is unknown.

<h3 id="alphas"><code>alphas</code></h3>

``` python
alphas()
```



<h3 id="assignments"><code>assignments</code></h3>

``` python
assignments()
```

Returns a list of Tensors with the matrix of assignments per shard.

<h3 id="clusters"><code>clusters</code></h3>

``` python
clusters()
```

Returns the clusters with dimensions num_classes X 1 X num_dimensions.

<h3 id="covariances"><code>covariances</code></h3>

``` python
covariances()
```

Returns the covariances matrices.

<h3 id="init_ops"><code>init_ops</code></h3>

``` python
init_ops()
```

Returns the initialization operation.

<h3 id="is_initialized"><code>is_initialized</code></h3>

``` python
is_initialized()
```

Returns a boolean operation for initialized variables.

<h3 id="scores"><code>scores</code></h3>

``` python
scores()
```

Returns the distances to each class.

#### Returns:

  A tuple with two Tensors. The first contains the distance to
each class. The second contains the distance to the assigned
class.

<h3 id="training_ops"><code>training_ops</code></h3>

``` python
training_ops()
```

Returns the training operation.



## Class Members

<h3 id="CLUSTERS_COVS_VARIABLE"><code>CLUSTERS_COVS_VARIABLE</code></h3>

<h3 id="CLUSTERS_VARIABLE"><code>CLUSTERS_VARIABLE</code></h3>

<h3 id="CLUSTERS_WEIGHT"><code>CLUSTERS_WEIGHT</code></h3>

