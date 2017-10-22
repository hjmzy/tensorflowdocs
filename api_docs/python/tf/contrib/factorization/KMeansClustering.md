<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.factorization.KMeansClustering" />
<meta itemprop="property" content="config"/>
<meta itemprop="property" content="model_dir"/>
<meta itemprop="property" content="model_fn"/>
<meta itemprop="property" content="params"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="cluster_centers"/>
<meta itemprop="property" content="evaluate"/>
<meta itemprop="property" content="export_savedmodel"/>
<meta itemprop="property" content="get_variable_names"/>
<meta itemprop="property" content="get_variable_value"/>
<meta itemprop="property" content="latest_checkpoint"/>
<meta itemprop="property" content="predict"/>
<meta itemprop="property" content="predict_cluster_index"/>
<meta itemprop="property" content="score"/>
<meta itemprop="property" content="train"/>
<meta itemprop="property" content="transform"/>
<meta itemprop="property" content="ALL_DISTANCES"/>
<meta itemprop="property" content="CLUSTER_INDEX"/>
<meta itemprop="property" content="COSINE_DISTANCE"/>
<meta itemprop="property" content="KMEANS_PLUS_PLUS_INIT"/>
<meta itemprop="property" content="RANDOM_INIT"/>
<meta itemprop="property" content="SCORE"/>
<meta itemprop="property" content="SQUARED_EUCLIDEAN_DISTANCE"/>
</div>

# tf.contrib.factorization.KMeansClustering

## Class `KMeansClustering`

Inherits From: [`Estimator`](../../../tf/estimator/Estimator.md)



Defined in [`tensorflow/contrib/factorization/python/ops/kmeans.py`](https://www.tensorflow.org/code/tensorflow/contrib/factorization/python/ops/kmeans.py).

An Estimator for K-Means clustering.

## Properties

<h3 id="config"><code>config</code></h3>



<h3 id="model_dir"><code>model_dir</code></h3>



<h3 id="model_fn"><code>model_fn</code></h3>

Returns the model_fn which is bound to self.params.

#### Returns:

The model_fn with following signature:
  `def model_fn(features, labels, mode, config)`

<h3 id="params"><code>params</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    num_clusters,
    model_dir=None,
    initial_clusters=RANDOM_INIT,
    distance_metric=SQUARED_EUCLIDEAN_DISTANCE,
    random_seed=0,
    use_mini_batch=True,
    mini_batch_steps_per_iteration=1,
    kmeans_plus_plus_num_retries=2,
    relative_tolerance=None,
    config=None
)
```

Creates an Estimator for running KMeans training and inference.

This Estimator implements the following variants of the K-means algorithm:

If `use_mini_batch` is False, it runs standard full batch K-means. Each
training step runs a single iteration of K-Means and must process the full
input at once. To run in this mode, the `input_fn` passed to `train` must
return the entire input dataset.

If `use_mini_batch` is True, it runs a generalization of the mini-batch
K-means algorithm. It runs multiple iterations, where each iteration is
composed of `mini_batch_steps_per_iteration` steps. Each training step
accumulates the contribution from one mini-batch into temporary storage.
Every `mini_batch_steps_per_iteration` steps, the cluster centers are
updated and the temporary storage cleared for the next iteration. Note
that:
  * If `mini_batch_steps_per_iteration=1`, the algorithm reduces to the
    standard K-means mini-batch algorithm.
  * If `mini_batch_steps_per_iteration = num_inputs / batch_size`, the
    algorithm becomes an asynchronous version of the full-batch algorithm.
    However, there is no guarantee by this implementation that each input
    is seen exactly once per iteration. Also, different updates are applied
    asynchronously without locking. So this asynchronous version may not
    behave exactly like a full-batch version.

#### Args:

* <b>`num_clusters`</b>: An integer tensor specifying the number of clusters. This
    argument is ignored if `initial_clusters` is a tensor or numpy array.
* <b>`model_dir`</b>: The directory to save the model results and log files.
* <b>`initial_clusters`</b>: Specifies how the initial cluster centers are chosen.
    One of the following:
    * a tensor or numpy array with the initial cluster centers.
    * a callable `f(inputs, k)` that selects and returns up to `k` centers
          from an input batch. `f` is free to return any number of centers
          from `0` to `k`. It will be invoked on successive input batches
          as necessary until all `num_clusters` centers are chosen.
    * `KMeansClustering.RANDOM_INIT`: Choose centers randomly from an input
          batch. If the batch size is less than `num_clusters` then the
          entire batch is chosen to be initial cluster centers and the
          remaining centers are chosen from successive input batches.
    * `KMeansClustering.KMEANS_PLUS_PLUS_INIT`: Use kmeans++ to choose
          centers from the first input batch. If the batch size is less
          than `num_clusters`, a TensorFlow runtime error occurs.
* <b>`distance_metric`</b>: The distance metric used for clustering. One of:
    * `KMeansClustering.SQUARED_EUCLIDEAN_DISTANCE`: Euclidean distance
         between vectors `u` and `v` is defined as `||u - v||_2` which is
         the square root of the sum of the absolute squares of the elements'
         difference.
    * `KMeansClustering.COSINE_DISTANCE`: Cosine distance between vectors
         `u` and `v` is defined as `1 - (u . v) / (||u||_2 ||v||_2)`.
* <b>`random_seed`</b>: Python integer. Seed for PRNG used to initialize centers.
* <b>`use_mini_batch`</b>: A boolean specifying whether to use the mini-batch k-means
    algorithm. See explanation above.
* <b>`mini_batch_steps_per_iteration`</b>: The number of steps after which the
    updated cluster centers are synced back to a master copy. Used only if
    `use_mini_batch=True`. See explanation above.
* <b>`kmeans_plus_plus_num_retries`</b>: For each point that is sampled during
    kmeans++ initialization, this parameter specifies the number of
    additional points to draw from the current distribution before selecting
    the best. If a negative value is specified, a heuristic is used to
    sample `O(log(num_to_sample))` additional points. Used only if
    `initial_clusters=KMeansClustering.KMEANS_PLUS_PLUS_INIT`.
* <b>`relative_tolerance`</b>: A relative tolerance of change in the loss between
    iterations. Stops learning if the loss changes less than this amount.
    This may not work correctly if `use_mini_batch=True`.
* <b>`config`</b>: See [`tf.estimator.Estimator`](../../../tf/estimator/Estimator.md).


#### Raises:

* <b>`ValueError`</b>: An invalid argument was passed to `initial_clusters` or
    `distance_metric`.

<h3 id="cluster_centers"><code>cluster_centers</code></h3>

``` python
cluster_centers()
```

Returns the cluster centers.

<h3 id="evaluate"><code>evaluate</code></h3>

``` python
evaluate(
    input_fn,
    steps=None,
    hooks=None,
    checkpoint_path=None,
    name=None
)
```

Evaluates the model given evaluation data input_fn.

For each step, calls `input_fn`, which returns one batch of data.
Evaluates until:
- `steps` batches are processed, or
- `input_fn` raises an end-of-input exception (`OutOfRangeError` or
`StopIteration`).

#### Args:

* <b>`input_fn`</b>: Input function returning a tuple of:
      features - Dictionary of string feature name to `Tensor` or
        `SparseTensor`.
      labels - `Tensor` or dictionary of `Tensor` with labels.
* <b>`steps`</b>: Number of steps for which to evaluate model. If `None`, evaluates
    until `input_fn` raises an end-of-input exception.
* <b>`hooks`</b>: List of `SessionRunHook` subclass instances. Used for callbacks
    inside the evaluation call.
* <b>`checkpoint_path`</b>: Path of a specific checkpoint to evaluate. If `None`, the
    latest checkpoint in `model_dir` is used.
* <b>`name`</b>: Name of the evaluation if user needs to run multiple evaluations on
    different data sets, such as on training data vs test data. Metrics for
    different evaluations are saved in separate folders, and appear
    separately in tensorboard.


#### Returns:

A dict containing the evaluation metrics specified in `model_fn` keyed by
name, as well as an entry `global_step` which contains the value of the
global step for which this evaluation was performed.


#### Raises:

* <b>`ValueError`</b>: If `steps <= 0`.
* <b>`ValueError`</b>: If no model has been trained, namely `model_dir`, or the
    given `checkpoint_path` is empty.

<h3 id="export_savedmodel"><code>export_savedmodel</code></h3>

``` python
export_savedmodel(
    export_dir_base,
    serving_input_receiver_fn,
    assets_extra=None,
    as_text=False,
    checkpoint_path=None
)
```

Exports inference graph as a SavedModel into given dir.

This method builds a new graph by first calling the
serving_input_receiver_fn to obtain feature `Tensor`s, and then calling
this `Estimator`'s model_fn to generate the model graph based on those
features. It restores the given checkpoint (or, lacking that, the most
recent checkpoint) into this graph in a fresh session.  Finally it creates
a timestamped export directory below the given export_dir_base, and writes
a `SavedModel` into it containing a single `MetaGraphDef` saved from this
session.

The exported `MetaGraphDef` will provide one `SignatureDef` for each
element of the export_outputs dict returned from the model_fn, named using
the same keys.  One of these keys is always
signature_constants.DEFAULT_SERVING_SIGNATURE_DEF_KEY, indicating which
signature will be served when a serving request does not specify one.
For each signature, the outputs are provided by the corresponding
`ExportOutput`s, and the inputs are always the input receivers provided by
the serving_input_receiver_fn.

Extra assets may be written into the SavedModel via the extra_assets
argument.  This should be a dict, where each key gives a destination path
(including the filename) relative to the assets.extra directory.  The
corresponding value gives the full path of the source file to be copied.
For example, the simple case of copying a single file without renaming it
is specified as `{'my_asset_file.txt': '/path/to/my_asset_file.txt'}`.

#### Args:

* <b>`export_dir_base`</b>: A string containing a directory in which to create
    timestamped subdirectories containing exported SavedModels.
* <b>`serving_input_receiver_fn`</b>: A function that takes no argument and
    returns a `ServingInputReceiver`.
* <b>`assets_extra`</b>: A dict specifying how to populate the assets.extra directory
    within the exported SavedModel, or `None` if no extra assets are needed.
* <b>`as_text`</b>: whether to write the SavedModel proto in text format.
* <b>`checkpoint_path`</b>: The checkpoint path to export.  If `None` (the default),
    the most recent checkpoint found within the model directory is chosen.


#### Returns:

The string path to the exported directory.


#### Raises:

* <b>`ValueError`</b>: if no serving_input_receiver_fn is provided, no export_outputs
      are provided, or no checkpoint can be found.

<h3 id="get_variable_names"><code>get_variable_names</code></h3>

``` python
get_variable_names()
```

Returns list of all variable names in this model.

#### Returns:

List of names.


#### Raises:

* <b>`ValueError`</b>: If the Estimator has not produced a checkpoint yet.

<h3 id="get_variable_value"><code>get_variable_value</code></h3>

``` python
get_variable_value(name)
```

Returns value of the variable given by name.

#### Args:

* <b>`name`</b>: string or a list of string, name of the tensor.


#### Returns:

Numpy array - value of the tensor.


#### Raises:

* <b>`ValueError`</b>: If the Estimator has not produced a checkpoint yet.

<h3 id="latest_checkpoint"><code>latest_checkpoint</code></h3>

``` python
latest_checkpoint()
```

Finds the filename of latest saved checkpoint file in `model_dir`.

#### Returns:

The full path to the latest checkpoint or `None` if no checkpoint was
found.

<h3 id="predict"><code>predict</code></h3>

``` python
predict(
    input_fn,
    predict_keys=None,
    hooks=None,
    checkpoint_path=None
)
```

Yields predictions for given features.

#### Args:

* <b>`input_fn`</b>: Input function returning features which is a dictionary of
    string feature name to `Tensor` or `SparseTensor`. If it returns a
    tuple, first item is extracted as features. Prediction continues until
    `input_fn` raises an end-of-input exception (`OutOfRangeError` or
    `StopIteration`).
* <b>`predict_keys`</b>: list of `str`, name of the keys to predict. It is used if
    the `EstimatorSpec.predictions` is a `dict`. If `predict_keys` is used
    then rest of the predictions will be filtered from the dictionary. If
    `None`, returns all.
* <b>`hooks`</b>: List of `SessionRunHook` subclass instances. Used for callbacks
    inside the prediction call.
* <b>`checkpoint_path`</b>: Path of a specific checkpoint to predict. If `None`, the
    latest checkpoint in `model_dir` is used.


#### Yields:

Evaluated values of `predictions` tensors.


#### Raises:

* <b>`ValueError`</b>: Could not find a trained model in model_dir.
* <b>`ValueError`</b>: if batch length of predictions are not same.
* <b>`ValueError`</b>: If there is a conflict between `predict_keys` and
    `predictions`. For example if `predict_keys` is not `None` but
    `EstimatorSpec.predictions` is not a `dict`.

<h3 id="predict_cluster_index"><code>predict_cluster_index</code></h3>

``` python
predict_cluster_index(input_fn)
```

Finds the index of the closest cluster center to each input point.

#### Args:

* <b>`input_fn`</b>: Input points. See [`tf.estimator.Estimator.predict`](../../../tf/estimator/Estimator.md#predict).


#### Yields:

The index of the closest cluster center for each input point.

<h3 id="score"><code>score</code></h3>

``` python
score(input_fn)
```

Returns the sum of squared distances to nearest clusters.

Note that this function is different from the corresponding one in sklearn
which returns the negative sum.

#### Args:

* <b>`input_fn`</b>: Input points. See [`tf.estimator.Estimator.evaluate`](../../../tf/estimator/Estimator.md#evaluate). Only one
      batch is retrieved.


#### Returns:

The sum of the squared distance from each point in the first batch of
inputs to its nearest cluster center.

<h3 id="train"><code>train</code></h3>

``` python
train(
    input_fn,
    hooks=None,
    steps=None,
    max_steps=None,
    saving_listeners=None
)
```

Trains a model given training data input_fn.

#### Args:

* <b>`input_fn`</b>: Input function returning a tuple of:
      features - `Tensor` or dictionary of string feature name to `Tensor`.
      labels - `Tensor` or dictionary of `Tensor` with labels.
* <b>`hooks`</b>: List of `SessionRunHook` subclass instances. Used for callbacks
    inside the training loop.
* <b>`steps`</b>: Number of steps for which to train model. If `None`, train forever
    or train until input_fn generates the `OutOfRange` error or
    `StopIteration` exception. 'steps' works incrementally. If you call two
    times train(steps=10) then training occurs in total 20 steps. If
    `OutOfRange` or `StopIteration` occurs in the middle, training stops
    before 20 steps. If you don't want to have incremental behavior please
    set `max_steps` instead. If set, `max_steps` must be `None`.
* <b>`max_steps`</b>: Number of total steps for which to train model. If `None`,
    train forever or train until input_fn generates the `OutOfRange` error
    or `StopIteration` exception. If set, `steps` must be `None`. If
    `OutOfRange` or `StopIteration` occurs in the middle, training stops
    before `max_steps` steps.
    Two calls to `train(steps=100)` means 200 training
    iterations. On the other hand, two calls to `train(max_steps=100)` means
    that the second call will not do any iteration since first call did
    all 100 steps.
* <b>`saving_listeners`</b>: list of `CheckpointSaverListener` objects. Used for
    callbacks that run immediately before or after checkpoint savings.


#### Returns:

`self`, for chaining.


#### Raises:

* <b>`ValueError`</b>: If both `steps` and `max_steps` are not `None`.
* <b>`ValueError`</b>: If either `steps` or `max_steps` is <= 0.

<h3 id="transform"><code>transform</code></h3>

``` python
transform(input_fn)
```

Transforms each input point to its distances to all cluster centers.

Note that if `distance_metric=KMeansClustering.SQUARED_EUCLIDEAN_DISTANCE`,
this
function returns the squared Euclidean distance while the corresponding
sklearn function returns the Euclidean distance.

#### Args:

* <b>`input_fn`</b>: Input points. See [`tf.estimator.Estimator.predict`](../../../tf/estimator/Estimator.md#predict).


#### Yields:

The distances from each input point to each cluster center.



## Class Members

<h3 id="ALL_DISTANCES"><code>ALL_DISTANCES</code></h3>

<h3 id="CLUSTER_INDEX"><code>CLUSTER_INDEX</code></h3>

<h3 id="COSINE_DISTANCE"><code>COSINE_DISTANCE</code></h3>

<h3 id="KMEANS_PLUS_PLUS_INIT"><code>KMEANS_PLUS_PLUS_INIT</code></h3>

<h3 id="RANDOM_INIT"><code>RANDOM_INIT</code></h3>

<h3 id="SCORE"><code>SCORE</code></h3>

<h3 id="SQUARED_EUCLIDEAN_DISTANCE"><code>SQUARED_EUCLIDEAN_DISTANCE</code></h3>

