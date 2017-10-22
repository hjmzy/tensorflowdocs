<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.stateless" />
</div>

# Module: tf.contrib.stateless



Defined in [`tensorflow/contrib/stateless/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/stateless/__init__.py).

Stateless random ops which take seed as a tensor input.

Instead of taking `seed` as an attr which initializes a mutable state within
the op, these random ops take `seed` as an input, and the random numbers are
a deterministic function of `shape` and `seed`.

WARNING: These ops are in contrib, and are not stable.  They should be
consistent across multiple runs on the same hardware, but only for the same
version of the code.


## Functions

[`stateless_random_normal(...)`](../../tf/contrib/stateless/stateless_random_normal.md): Outputs deterministic pseudorandom values from a normal distribution.

[`stateless_random_uniform(...)`](../../tf/contrib/stateless/stateless_random_uniform.md): Outputs deterministic pseudorandom random values from a uniform distribution.

[`stateless_truncated_normal(...)`](../../tf/contrib/stateless/stateless_truncated_normal.md): Outputs deterministic pseudorandom values from a truncated normal distribution.

