<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.opt" />
</div>

# Module: tf.contrib.opt



Defined in [`tensorflow/contrib/opt/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/opt/__init__.py).

A module containing optimization routines.

## Classes

[`class DropStaleGradientOptimizer`](../../tf/contrib/opt/DropStaleGradientOptimizer.md): Wrapper optimizer that checks and drops stale gradient.

[`class ExternalOptimizerInterface`](../../tf/contrib/opt/ExternalOptimizerInterface.md): Base class for interfaces with external optimization algorithms.

[`class LazyAdamOptimizer`](../../tf/contrib/opt/LazyAdamOptimizer.md): Variant of the Adam optimizer that handles sparse updates more efficiently.

[`class MovingAverageOptimizer`](../../tf/contrib/opt/MovingAverageOptimizer.md): Optimizer that computes a moving average of the variables.

[`class NadamOptimizer`](../../tf/contrib/opt/NadamOptimizer.md): Optimizer that implements the Nadam algorithm.

[`class ScipyOptimizerInterface`](../../tf/contrib/opt/ScipyOptimizerInterface.md): Wrapper allowing `scipy.optimize.minimize` to operate a `tf.Session`.

[`class VariableClippingOptimizer`](../../tf/contrib/opt/VariableClippingOptimizer.md): Wrapper optimizer that clips the norm of specified variables after update.

