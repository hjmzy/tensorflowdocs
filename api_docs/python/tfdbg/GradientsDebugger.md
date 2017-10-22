<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tfdbg.GradientsDebugger" />
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="y_tensor"/>
<meta itemprop="property" content="__enter__"/>
<meta itemprop="property" content="__exit__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="gradient_tensor"/>
<meta itemprop="property" content="gradient_tensors"/>
<meta itemprop="property" content="identify_gradient"/>
<meta itemprop="property" content="register_gradient_tensor"/>
<meta itemprop="property" content="watch_gradients_by_tensor_names"/>
<meta itemprop="property" content="watch_gradients_by_tensors"/>
</div>

# tfdbg.GradientsDebugger

## Class `GradientsDebugger`





Defined in [`tensorflow/python/debug/lib/debug_gradients.py`](https://www.tensorflow.org/code/tensorflow/python/debug/lib/debug_gradients.py).

Gradients Debugger.

Allows retrieval of gradient tensors created by TensorFlow's automatic
differentiation algorithm, i.e., [`tf.gradients`](../tf/gradients.md) and optimizer classes that
use it.

## Properties

<h3 id="graph"><code>graph</code></h3>



<h3 id="y_tensor"><code>y_tensor</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(y_tensor=None)
```

Constructor of GradientsDebugger.

#### Args:

* <b>`y_tensor`</b>: optional: the `tf.Tensor` to be differentiated, i.e., the tensor
    on the numerator of the differentiation.

<h3 id="__enter__"><code>__enter__</code></h3>

``` python
__enter__()
```



<h3 id="__exit__"><code>__exit__</code></h3>

``` python
__exit__(
    unused_type,
    unused_value,
    unused_traceback
)
```



<h3 id="gradient_tensor"><code>gradient_tensor</code></h3>

``` python
gradient_tensor(x_tensor)
```

Get the gradient tensor of an x-tensor.

#### Args:

* <b>`x_tensor`</b>: (`tf.Tensor`, `tf.Variable` or `str`) The x-tensor object or its
    name. x-tensor refers to the independent `tf.Tensor`, i.e., the tensor
    on the denominator of the differentiation.


#### Returns:

If found, the gradient tensor.


#### Raises:

* <b>`TypeError`</b>: If `x_tensor` is not a `tf.Tensor`, `tf.Variable` or `str`.
* <b>`LookupError`</b>: If the `x_tensor` has not been registered with a gradient
    tensor.

<h3 id="gradient_tensors"><code>gradient_tensors</code></h3>

``` python
gradient_tensors()
```

Get the gradient tensors that this object is aware of.

#### Returns:

A dict mapping x-tensor names to gradient tensor objects. x-tensor refers
to the tensors on the denominator of the differentation.

<h3 id="identify_gradient"><code>identify_gradient</code></h3>

``` python
identify_gradient(input_tensor)
```

Create a debug identity tensor that registers and forwards gradients.

The side effect of this method is that when gradient tensor(s) are created
with respect to the any paths that include the `input_tensor`, the gradient
tensor(s) with repsect to `input_tensor` will be registered with this
this `GradientsDebugger` instance and can later be retrieved, with the
methods `gradient_tensor` and `gradient_tensors`.

Example:

```python
x = tf.Variable(1.0)
y = tf.add(x, x)

grad_debugger = tf_debug.GradientsDebugger()
debug_y = grad_debugger.identify_gradient(y)
z = tf.square(debug_y)

# Create a train op under the grad_debugger context.
with grad_debugger:
  train_op = tf.train.GradientDescentOptimizer(z)

# Now we can reflect through grad_debugger to get the gradient tensor
# with respect to y.
y_grad = grad_debugger.gradient_tensor(y)
```

#### Args:

* <b>`input_tensor`</b>: the input `tf.Tensor` object whose related gradient tensors
    are to be reigstered with this `GradientsDebugger` instance when they
    are created, e.g., during [`tf.gradients`](../tf/gradients.md) calls or the construction
    of optimization (training) op that uses [`tf.gradients`](../tf/gradients.md).


#### Returns:

A forwarded identity of `input_tensor`, as a `tf.Tensor`.


#### Raises:

* <b>`ValueError`</b>: If an op with name that duplicates the gradient-debugging op
    already exists in the graph (highly unlikely).

<h3 id="register_gradient_tensor"><code>register_gradient_tensor</code></h3>

``` python
register_gradient_tensor(
    x_tensor_name,
    gradient_tensor
)
```

Register the gradient tensor for an x-tensor.

#### Args:

* <b>`x_tensor_name`</b>: (`str`) the name of the independent `tf.Tensor`, i.e.,
    the tensor on the denominator of the differentiation.
* <b>`gradient_tensor`</b>: the gradient `tf.Tensor`.

<h3 id="watch_gradients_by_tensor_names"><code>watch_gradients_by_tensor_names</code></h3>

``` python
watch_gradients_by_tensor_names(
    graph,
    tensor_name_regex
)
```

Watch gradient tensors by name(s) of the x-tensor(s).

The side effect of this method is that when gradient tensor(s) are created
with respect to the x-tensors, the gradient tensor(s) will be registered
with this `GradientsDebugger` instance and can later be retrieved.

Unlike the `identify_gradient` method, this method is used after the
construction of the forward graph has completed. Unlike the
`watch_gradients_by_tensor` method, this method does not use handles to the
tensors of interest; it uses their names.

This method is the same as `watch_gradients_by_tensors` except that the
x-tensors are specified by name patterns, instead of `tf.Tensor` or
`tf.Variable` objects.

Example:

```python
x = tf.Variable(1.0, name="x")
y = tf.add(x, x, name="y")
z = tf.square(debug_y)

# Create a train op under the grad_debugger context.
grad_debugger = tf_debug.GradientsDebugger()
with grad_debugger.watch_gradients_by_tensor_names(r"(x|y):0$"):
  train_op = tf.train.GradientDescentOptimizer(z)

# Now we can reflect through grad_debugger to get the gradient tensor
# with respect to x and y.
x_grad = grad_debugger.gradient_tensor("x:0")
y_grad = grad_debugger.gradient_tensor("y:0")
```

#### Args:

* <b>`graph`</b>: the `tf.Graph` to watch the gradients on.
* <b>`tensor_name_regex`</b>: the regular-expression pattern of the name(s) of the
    x-tensor(s) to watch. x-tensor refers to the tensors on the denominator
    of the differentiation.


#### Returns:

The GradientsDebugger instance itself.

<h3 id="watch_gradients_by_tensors"><code>watch_gradients_by_tensors</code></h3>

``` python
watch_gradients_by_tensors(
    graph,
    tensors
)
```

Watch gradient tensors by x-tensor(s).

The side effect of this method is that when gradient tensor(s) are created
with respect to the any paths that include the `x_tensor`s, the gradient
tensor(s) with repsect to the tensor will be registered with this
this `GradientsDebugger` instance and can later be retrieved, with the
methods `gradient_tensor` and `gradient_tensors`.

Unlike the method `identify_gradient`, this method is used to retrieve
gradient tensors after the construction of the forward subgraph has
completed (but before the construction of the backward subgraph).

This method is the same as `watch_gradients_by_x_tensor_names` except that
the tensors are specified by the Python `tf.Tensor` or `tf.Variable`
objects, instead by name patterns.

Example:

```python
x = tf.Variable(1.0)
y = tf.add(x, x, name="y")
z = tf.square(debug_y)

# Create a train op under the grad_debugger context.
grad_debugger = tf_debug.GradientsDebugger()
with grad_debugger.watch_gradients_by_tensors(y):
  train_op = tf.train.GradientDescentOptimizer(z)

# Now we can reflect through grad_debugger to get the gradient tensor
# with respect to y.
y_grad = grad_debugger.gradient_tensor(y)
# or
y_grad = grad_debugger.gradient_tensor("y:0")
```

#### Args:

* <b>`graph`</b>: the `tf.Graph` to watch the gradients on.
* <b>`tensors`</b>: a `tf.Tensor` or `tf.Variable` object, or a list of such objects.


#### Returns:

The GradientsDebugger instance itself.



