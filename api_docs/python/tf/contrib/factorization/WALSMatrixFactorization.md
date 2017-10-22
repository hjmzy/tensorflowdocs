<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.factorization.WALSMatrixFactorization" />
<meta itemprop="property" content="config"/>
<meta itemprop="property" content="model_dir"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="evaluate"/>
<meta itemprop="property" content="export"/>
<meta itemprop="property" content="export_savedmodel"/>
<meta itemprop="property" content="fit"/>
<meta itemprop="property" content="get_col_factors"/>
<meta itemprop="property" content="get_params"/>
<meta itemprop="property" content="get_projections"/>
<meta itemprop="property" content="get_row_factors"/>
<meta itemprop="property" content="get_variable_names"/>
<meta itemprop="property" content="get_variable_value"/>
<meta itemprop="property" content="partial_fit"/>
<meta itemprop="property" content="predict"/>
<meta itemprop="property" content="set_params"/>
<meta itemprop="property" content="COMPLETED_SWEEPS"/>
<meta itemprop="property" content="INPUT_COLS"/>
<meta itemprop="property" content="INPUT_ROWS"/>
<meta itemprop="property" content="PROJECTION_RESULT"/>
<meta itemprop="property" content="PROJECTION_WEIGHTS"/>
<meta itemprop="property" content="PROJECT_ROW"/>
</div>

# tf.contrib.factorization.WALSMatrixFactorization

## Class `WALSMatrixFactorization`

Inherits From: [`Estimator`](../../../tf/contrib/learn/Estimator.md)



Defined in [`tensorflow/contrib/factorization/python/ops/wals.py`](https://www.tensorflow.org/code/tensorflow/contrib/factorization/python/ops/wals.py).

An Estimator for Weighted Matrix Factorization, using the WALS method.

WALS (Weighted Alternating Least Squares) is an algorithm for weighted matrix
factorization. It computes a low-rank approximation of a given sparse (n x m)
matrix A, by a product of two matrices, U * V^T, where U is a (n x k) matrix
and V is a (m x k) matrix. Here k is the rank of the approximation, also
called the embedding dimension. We refer to U as the row factors, and V as the
column factors.
See tensorflow/contrib/factorization/g3doc/wals.md for the precise problem
formulation.

The training proceeds in sweeps: during a row_sweep, we fix V and solve for U.
During a column sweep, we fix U and solve for V. Each one of these problems is
an unconstrained quadratic minimization problem and can be solved exactly (it
can also be solved in mini-batches, since the solution decouples nicely).
The alternating between sweeps is achieved by using a hook during training,
which is responsible for keeping track of the sweeps and running preparation
ops at the beginning of each sweep. It also updates the global_step variable,
which keeps track of the number of batches processed since the beginning of
training.
The current implementation assumes that the training is run on a single
machine, and will fail if config.num_worker_replicas is not equal to one.
Training is done by calling self.fit(input_fn=input_fn), where input_fn
provides two tensors: one for rows of the input matrix, and one for rows of
the transposed input matrix (i.e. columns of the original matrix). Note that
during a row sweep, only row batches are processed (ignoring column batches)
and vice-versa.
Also note that every row (respectively every column) of the input matrix
must be processed at least once for the sweep to be considered complete. In
particular, training will not make progress if input_fn does not generate some
rows.

For prediction, given a new set of input rows A' (e.g. new rows of the A
matrix), we compute a corresponding set of row factors U', such that U' * V^T
is a good approximation of A'. We call this operation a row projection. A
similar operation is defined for columns.
Projection is done by calling self.get_projections(input_fn=input_fn), where
input_fn satisfies the constraints given below.

The input functions must satisfy the following constraints: Calling input_fn
must return a tuple (features, labels) where labels is None, and features is
a dict containing the following keys:
TRAIN:
  - WALSMatrixFactorization.INPUT_ROWS: float32 SparseTensor (matrix).
    Rows of the input matrix to process (or to project).
  - WALSMatrixFactorization.INPUT_COLS: float32 SparseTensor (matrix).
    Columns of the input matrix to process (or to project), transposed.
INFER:
  - WALSMatrixFactorization.INPUT_ROWS: float32 SparseTensor (matrix).
    Rows to project.
  - WALSMatrixFactorization.INPUT_COLS: float32 SparseTensor (matrix).
    Columns to project.
  - WALSMatrixFactorization.PROJECT_ROW: Boolean Tensor. Whether to project
    the rows or columns.
  - WALSMatrixFactorization.PROJECTION_WEIGHTS (Optional): float32 Tensor
    (vector). The weights to use in the projection.
EVAL:
  - WALSMatrixFactorization.INPUT_ROWS: float32 SparseTensor (matrix).
    Rows to project.
  - WALSMatrixFactorization.INPUT_COLS: float32 SparseTensor (matrix).
    Columns to project.
  - WALSMatrixFactorization.PROJECT_ROW: Boolean Tensor. Whether to project
    the rows or columns.

## Properties

<h3 id="config"><code>config</code></h3>



<h3 id="model_dir"><code>model_dir</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    num_rows,
    num_cols,
    embedding_dimension,
    unobserved_weight=0.1,
    regularization_coeff=None,
    row_init='random',
    col_init='random',
    num_row_shards=1,
    num_col_shards=1,
    row_weights=1,
    col_weights=1,
    use_factors_weights_cache_for_training=True,
    use_gramian_cache_for_training=True,
    max_sweeps=None,
    model_dir=None,
    config=None
)
```

Creates a model for matrix factorization using the WALS method.

#### Args:

* <b>`num_rows`</b>: Total number of rows for input matrix.
* <b>`num_cols`</b>: Total number of cols for input matrix.
* <b>`embedding_dimension`</b>: Dimension to use for the factors.
* <b>`unobserved_weight`</b>: Weight of the unobserved entries of matrix.
* <b>`regularization_coeff`</b>: Weight of the L2 regularization term. Defaults to
    None, in which case the problem is not regularized.
* <b>`row_init`</b>: Initializer for row factor. Must be either:
    - A tensor: The row factor matrix is initialized to this tensor,
    - A numpy constant,
    - "random": The rows are initialized using a normal distribution.
* <b>`col_init`</b>: Initializer for column factor. See row_init.
* <b>`num_row_shards`</b>: Number of shards to use for the row factors.
* <b>`num_col_shards`</b>: Number of shards to use for the column factors.
* <b>`row_weights`</b>: Must be in one of the following three formats:
    - None: In this case, the weight of every entry is the unobserved_weight
      and the problem simplifies to ALS. Note that, in this case,
      col_weights must also be set to "None".
    - List of lists of non-negative scalars, of the form
      [[w_0, w_1, ...], [w_k, ... ], [...]],
      where the number of inner lists equal to the number of row factor
      shards and the elements in each inner list are the weights for the
      rows of that shard. In this case,
      w_ij = unonbserved_weight + row_weights[i] * col_weights[j].
    - A non-negative scalar: This value is used for all row weights.
      Note that it is allowed to have row_weights as a list and col_weights
      as a scalar, or vice-versa.
* <b>`col_weights`</b>: See row_weights.
* <b>`use_factors_weights_cache_for_training`</b>: Boolean, whether the factors and
    weights will be cached on the workers before the updates start, during
    training. Defaults to True.
    Note that caching is disabled during prediction.
* <b>`use_gramian_cache_for_training`</b>: Boolean, whether the Gramians will be
    cached on the workers before the updates start, during training.
    Defaults to True. Note that caching is disabled during prediction.
* <b>`max_sweeps`</b>: integer, optional. Specifies the number of sweeps for which
    to train the model, where a sweep is defined as a full update of all the
    row factors (resp. column factors).
    If `steps` or `max_steps` is also specified in model.fit(), training
    stops when either of the steps condition or sweeps condition is met.
* <b>`model_dir`</b>: The directory to save the model results and log files.
* <b>`config`</b>: A Configuration object. See Estimator.


#### Raises:

* <b>`ValueError`</b>: If config.num_worker_replicas is strictly greater than one.
    The current implementation only supports running on a single worker.

<h3 id="evaluate"><code>evaluate</code></h3>

``` python
evaluate(
    x=None,
    y=None,
    input_fn=None,
    feed_fn=None,
    batch_size=None,
    steps=None,
    metrics=None,
    name=None,
    checkpoint_path=None,
    hooks=None,
    log_progress=True
)
```

See `Evaluable`. (deprecated arguments)

SOME ARGUMENTS ARE DEPRECATED. They will be removed after 2016-12-01.
Instructions for updating:
Estimator is decoupled from Scikit Learn interface by moving into
separate class SKCompat. Arguments x, y and batch_size are only
available in the SKCompat class, Estimator will only accept input_fn.
Example conversion:
  est = Estimator(...) -> est = SKCompat(Estimator(...))

#### Raises:

* <b>`ValueError`</b>: If at least one of `x` or `y` is provided, and at least one of
      `input_fn` or `feed_fn` is provided.
      Or if `metrics` is not `None` or `dict`.

<h3 id="export"><code>export</code></h3>

``` python
export(
    export_dir,
    input_fn=export._default_input_fn,
    input_feature_key=None,
    use_deprecated_input_fn=True,
    signature_fn=None,
    prediction_key=None,
    default_batch_size=1,
    exports_to_keep=None,
    checkpoint_path=None
)
```

Exports inference graph into given dir. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2017-03-25.
Instructions for updating:
Please use Estimator.export_savedmodel() instead.

#### Args:

* <b>`export_dir`</b>: A string containing a directory to write the exported graph
    and checkpoints.
* <b>`input_fn`</b>: If `use_deprecated_input_fn` is true, then a function that given
    `Tensor` of `Example` strings, parses it into features that are then
    passed to the model. Otherwise, a function that takes no argument and
    returns a tuple of (features, labels), where features is a dict of
    string key to `Tensor` and labels is a `Tensor` that's currently not
    used (and so can be `None`).
* <b>`input_feature_key`</b>: Only used if `use_deprecated_input_fn` is false. String
    key into the features dict returned by `input_fn` that corresponds to a
    the raw `Example` strings `Tensor` that the exported model will take as
    input. Can only be `None` if you're using a custom `signature_fn` that
    does not use the first arg (examples).
* <b>`use_deprecated_input_fn`</b>: Determines the signature format of `input_fn`.
* <b>`signature_fn`</b>: Function that returns a default signature and a named
    signature map, given `Tensor` of `Example` strings, `dict` of `Tensor`s
    for features and `Tensor` or `dict` of `Tensor`s for predictions.
* <b>`prediction_key`</b>: The key for a tensor in the `predictions` dict (output
    from the `model_fn`) to use as the `predictions` input to the
    `signature_fn`. Optional. If `None`, predictions will pass to
    `signature_fn` without filtering.
* <b>`default_batch_size`</b>: Default batch size of the `Example` placeholder.
* <b>`exports_to_keep`</b>: Number of exports to keep.
* <b>`checkpoint_path`</b>: the checkpoint path of the model to be exported. If it is
      `None` (which is default), will use the latest checkpoint in
      export_dir.


#### Returns:

The string path to the exported directory. NB: this functionality was
added ca. 2016/09/25; clients that depend on the return value may need
to handle the case where this function returns None because subclasses
are not returning a value.

<h3 id="export_savedmodel"><code>export_savedmodel</code></h3>

``` python
export_savedmodel(
    export_dir_base,
    serving_input_fn,
    default_output_alternative_key=None,
    assets_extra=None,
    as_text=False,
    checkpoint_path=None,
    graph_rewrite_specs=(GraphRewriteSpec((tag_constants.SERVING,), ()),)
)
```

Exports inference graph as a SavedModel into given dir.

#### Args:

* <b>`export_dir_base`</b>: A string containing a directory to write the exported
    graph and checkpoints.
* <b>`serving_input_fn`</b>: A function that takes no argument and
    returns an `InputFnOps`.
* <b>`default_output_alternative_key`</b>: the name of the head to serve when none is
    specified.  Not needed for single-headed models.
* <b>`assets_extra`</b>: A dict specifying how to populate the assets.extra directory
    within the exported SavedModel.  Each key should give the destination
    path (including the filename) relative to the assets.extra directory.
    The corresponding value gives the full path of the source file to be
    copied.  For example, the simple case of copying a single file without
    renaming it is specified as
    `{'my_asset_file.txt': '/path/to/my_asset_file.txt'}`.
* <b>`as_text`</b>: whether to write the SavedModel proto in text format.
* <b>`checkpoint_path`</b>: The checkpoint path to export.  If None (the default),
    the most recent checkpoint found within the model directory is chosen.
* <b>`graph_rewrite_specs`</b>: an iterable of `GraphRewriteSpec`.  Each element will
    produce a separate MetaGraphDef within the exported SavedModel, tagged
    and rewritten as specified.  Defaults to a single entry using the
    default serving tag ("serve") and no rewriting.


#### Returns:

The string path to the exported directory.


#### Raises:

* <b>`ValueError`</b>: if an unrecognized export_type is requested.

<h3 id="fit"><code>fit</code></h3>

``` python
fit(
    x=None,
    y=None,
    input_fn=None,
    steps=None,
    batch_size=None,
    monitors=None,
    max_steps=None
)
```

See `Trainable`. (deprecated arguments)

SOME ARGUMENTS ARE DEPRECATED. They will be removed after 2016-12-01.
Instructions for updating:
Estimator is decoupled from Scikit Learn interface by moving into
separate class SKCompat. Arguments x, y and batch_size are only
available in the SKCompat class, Estimator will only accept input_fn.
Example conversion:
  est = Estimator(...) -> est = SKCompat(Estimator(...))

#### Raises:

* <b>`ValueError`</b>: If `x` or `y` are not `None` while `input_fn` is not `None`.
* <b>`ValueError`</b>: If both `steps` and `max_steps` are not `None`.

<h3 id="get_col_factors"><code>get_col_factors</code></h3>

``` python
get_col_factors()
```

Returns the column factors of the model, loading them from checkpoint.

Should only be run after training.

#### Returns:

A list of the column factors of the model.

<h3 id="get_params"><code>get_params</code></h3>

``` python
get_params(deep=True)
```

Get parameters for this estimator.

#### Args:

* <b>`deep`</b>: boolean, optional

    If `True`, will return the parameters for this estimator and
    contained subobjects that are estimators.


#### Returns:

* <b>`params `</b>: mapping of string to any
  Parameter names mapped to their values.

<h3 id="get_projections"><code>get_projections</code></h3>

``` python
get_projections(input_fn)
```

Computes the projections of the rows or columns given in input_fn.

Runs predict() with the given input_fn, and returns the results. Should only
be run after training.

#### Args:

* <b>`input_fn`</b>: Input function which specifies the rows or columns to project.

#### Returns:

A generator of the projected factors.

<h3 id="get_row_factors"><code>get_row_factors</code></h3>

``` python
get_row_factors()
```

Returns the row factors of the model, loading them from checkpoint.

Should only be run after training.

#### Returns:

A list of the row factors of the model.

<h3 id="get_variable_names"><code>get_variable_names</code></h3>

``` python
get_variable_names()
```

Returns list of all variable names in this model.

#### Returns:

List of names.

<h3 id="get_variable_value"><code>get_variable_value</code></h3>

``` python
get_variable_value(name)
```

Returns value of the variable given by name.

#### Args:

* <b>`name`</b>: string, name of the tensor.


#### Returns:

Numpy array - value of the tensor.

<h3 id="partial_fit"><code>partial_fit</code></h3>

``` python
partial_fit(
    x=None,
    y=None,
    input_fn=None,
    steps=1,
    batch_size=None,
    monitors=None
)
```

Incremental fit on a batch of samples. (deprecated arguments)

SOME ARGUMENTS ARE DEPRECATED. They will be removed after 2016-12-01.
Instructions for updating:
Estimator is decoupled from Scikit Learn interface by moving into
separate class SKCompat. Arguments x, y and batch_size are only
available in the SKCompat class, Estimator will only accept input_fn.
Example conversion:
  est = Estimator(...) -> est = SKCompat(Estimator(...))

This method is expected to be called several times consecutively
on different or the same chunks of the dataset. This either can
implement iterative training or out-of-core/online training.

This is especially useful when the whole dataset is too big to
fit in memory at the same time. Or when model is taking long time
to converge, and you want to split up training into subparts.

#### Args:

* <b>`x`</b>: Matrix of shape [n_samples, n_features...]. Can be iterator that
     returns arrays of features. The training input samples for fitting the
     model. If set, `input_fn` must be `None`.
* <b>`y`</b>: Vector or matrix [n_samples] or [n_samples, n_outputs]. Can be
     iterator that returns array of labels. The training label values
     (class labels in classification, real numbers in regression). If set,
     `input_fn` must be `None`.
* <b>`input_fn`</b>: Input function. If set, `x`, `y`, and `batch_size` must be
    `None`.
* <b>`steps`</b>: Number of steps for which to train model. If `None`, train forever.
* <b>`batch_size`</b>: minibatch size to use on the input, defaults to first
    dimension of `x`. Must be `None` if `input_fn` is provided.
* <b>`monitors`</b>: List of `BaseMonitor` subclass instances. Used for callbacks
    inside the training loop.


#### Returns:

`self`, for chaining.


#### Raises:

* <b>`ValueError`</b>: If at least one of `x` and `y` is provided, and `input_fn` is
      provided.

<h3 id="predict"><code>predict</code></h3>

``` python
predict(
    x=None,
    input_fn=None,
    batch_size=None,
    outputs=None,
    as_iterable=True
)
```

Returns predictions for given features. (deprecated arguments)

SOME ARGUMENTS ARE DEPRECATED. They will be removed after 2016-12-01.
Instructions for updating:
Estimator is decoupled from Scikit Learn interface by moving into
separate class SKCompat. Arguments x, y and batch_size are only
available in the SKCompat class, Estimator will only accept input_fn.
Example conversion:
  est = Estimator(...) -> est = SKCompat(Estimator(...))

#### Args:

* <b>`x`</b>: Matrix of shape [n_samples, n_features...]. Can be iterator that
     returns arrays of features. The training input samples for fitting the
     model. If set, `input_fn` must be `None`.
* <b>`input_fn`</b>: Input function. If set, `x` and 'batch_size' must be `None`.
* <b>`batch_size`</b>: Override default batch size. If set, 'input_fn' must be
    'None'.
* <b>`outputs`</b>: list of `str`, name of the output to predict.
    If `None`, returns all.
* <b>`as_iterable`</b>: If True, return an iterable which keeps yielding predictions
    for each example until inputs are exhausted. Note: The inputs must
    terminate if you want the iterable to terminate (e.g. be sure to pass
    num_epochs=1 if you are using something like read_batch_features).


#### Returns:

A numpy array of predicted classes or regression values if the
constructor's `model_fn` returns a `Tensor` for `predictions` or a `dict`
of numpy arrays if `model_fn` returns a `dict`. Returns an iterable of
predictions if as_iterable is True.


#### Raises:

* <b>`ValueError`</b>: If x and input_fn are both provided or both `None`.

<h3 id="set_params"><code>set_params</code></h3>

``` python
set_params(**params)
```

Set the parameters of this estimator.

The method works on simple estimators as well as on nested objects
(such as pipelines). The former have parameters of the form
``<component>__<parameter>`` so that it's possible to update each
component of a nested object.

#### Args:

* <b>`**params`</b>: Parameters.


#### Returns:

self


#### Raises:

* <b>`ValueError`</b>: If params contain invalid names.



## Class Members

<h3 id="COMPLETED_SWEEPS"><code>COMPLETED_SWEEPS</code></h3>

<h3 id="INPUT_COLS"><code>INPUT_COLS</code></h3>

<h3 id="INPUT_ROWS"><code>INPUT_ROWS</code></h3>

<h3 id="PROJECTION_RESULT"><code>PROJECTION_RESULT</code></h3>

<h3 id="PROJECTION_WEIGHTS"><code>PROJECTION_WEIGHTS</code></h3>

<h3 id="PROJECT_ROW"><code>PROJECT_ROW</code></h3>

