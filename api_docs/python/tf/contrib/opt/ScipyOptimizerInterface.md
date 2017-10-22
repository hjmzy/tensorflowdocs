<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.opt.ScipyOptimizerInterface" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="minimize"/>
</div>

# tf.contrib.opt.ScipyOptimizerInterface

## Class `ScipyOptimizerInterface`

Inherits From: [`ExternalOptimizerInterface`](../../../tf/contrib/opt/ExternalOptimizerInterface.md)



Defined in [`tensorflow/contrib/opt/python/training/external_optimizer.py`](https://www.tensorflow.org/code/tensorflow/contrib/opt/python/training/external_optimizer.py).

Wrapper allowing `scipy.optimize.minimize` to operate a `tf.Session`.

Example:

```python
vector = tf.Variable([7., 7.], 'vector')

# Make vector norm as small as possible.
loss = tf.reduce_sum(tf.square(vector))

optimizer = ScipyOptimizerInterface(loss, options={'maxiter': 100})

with tf.Session() as session:
  optimizer.minimize(session)

# The value of vector should now be [0., 0.].
```

Example with simple bound constraints:

```python
vector = tf.Variable([7., 7.], 'vector')

# Make vector norm as small as possible.
loss = tf.reduce_sum(tf.square(vector))

optimizer = ScipyOptimizerInterface(
    loss, var_to_bounds={vector: ([1, 2], np.infty)})

with tf.Session() as session:
  optimizer.minimize(session)

# The value of vector should now be [1., 2.].
```

Example with more complicated constraints:

```python
vector = tf.Variable([7., 7.], 'vector')

# Make vector norm as small as possible.
loss = tf.reduce_sum(tf.square(vector))
# Ensure the vector's y component is = 1.
equalities = [vector[1] - 1.]
# Ensure the vector's x component is >= 1.
inequalities = [vector[0] - 1.]

# Our default SciPy optimization algorithm, L-BFGS-B, does not support
# general constraints. Thus we use SLSQP instead.
optimizer = ScipyOptimizerInterface(
    loss, equalities=equalities, inequalities=inequalities, method='SLSQP')

with tf.Session() as session:
  optimizer.minimize(session)

# The value of vector should now be [1., 1.].
```

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    loss,
    var_list=None,
    equalities=None,
    inequalities=None,
    var_to_bounds=None,
    **optimizer_kwargs
)
```

Initialize a new interface instance.

#### Args:

* <b>`loss`</b>: A scalar `Tensor` to be minimized.
* <b>`var_list`</b>: Optional `list` of `Variable` objects to update to minimize
    `loss`.  Defaults to the list of variables collected in the graph
    under the key `GraphKeys.TRAINABLE_VARIABLES`.
* <b>`equalities`</b>: Optional `list` of equality constraint scalar `Tensor`s to be
    held equal to zero.
* <b>`inequalities`</b>: Optional `list` of inequality constraint scalar `Tensor`s
    to be held nonnegative.
* <b>`var_to_bounds`</b>: Optional `dict` where each key is an optimization
    `Variable` and each corresponding value is a length-2 tuple of
    `(low, high)` bounds. Although enforcing this kind of simple constraint
    could be accomplished with the `inequalities` arg, not all optimization
    algorithms support general inequality constraints, e.g. L-BFGS-B. Both
    `low` and `high` can either be numbers or anything convertible to a
    NumPy array that can be broadcast to the shape of `var` (using
    `np.broadcast_to`). To indicate that there is no bound, use `None` (or
    `+/- np.infty`). For example, if `var` is a 2x3 matrix, then any of
    the following corresponding `bounds` could be supplied:
    * `(0, np.infty)`: Each element of `var` held positive.
    * `(-np.infty, [1, 2])`: First column less than 1, second column less
      than 2.
    * `(-np.infty, [[1], [2], [3]])`: First row less than 1, second row less
      than 2, etc.
    * `(-np.infty, [[1, 2, 3], [4, 5, 6]])`: Entry `var[0, 0]` less than 1,
      `var[0, 1]` less than 2, etc.
* <b>`**optimizer_kwargs`</b>: Other subclass-specific keyword arguments.

<h3 id="minimize"><code>minimize</code></h3>

``` python
minimize(
    session=None,
    feed_dict=None,
    fetches=None,
    step_callback=None,
    loss_callback=None,
    **run_kwargs
)
```

Minimize a scalar `Tensor`.

Variables subject to optimization are updated in-place at the end of
optimization.

Note that this method does *not* just return a minimization `Op`, unlike
`Optimizer.minimize()`; instead it actually performs minimization by
executing commands to control a `Session`.

#### Args:

* <b>`session`</b>: A `Session` instance.
* <b>`feed_dict`</b>: A feed dict to be passed to calls to `session.run`.
* <b>`fetches`</b>: A list of `Tensor`s to fetch and supply to `loss_callback`
    as positional arguments.
* <b>`step_callback`</b>: A function to be called at each optimization step;
    arguments are the current values of all optimization variables
    flattened into a single vector.
* <b>`loss_callback`</b>: A function to be called every time the loss and gradients
    are computed, with evaluated fetches supplied as positional arguments.
* <b>`**run_kwargs`</b>: kwargs to pass to `session.run`.



