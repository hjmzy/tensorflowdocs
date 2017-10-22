<!-- DO NOT EDIT! Automatically generated file. -->
# Constants, Sequences, and Random Values

Note: Functions taking `Tensor` arguments can also take anything accepted by
[`tf.convert_to_tensor`](../../api_docs/python/tf/convert_to_tensor.md).

[TOC]

<h2 id="Constant_Value_Tensors">Constant Value Tensors</h2>

TensorFlow provides several operations that you can use to generate constants.

*   [`tf.zeros`](../../api_docs/python/tf/zeros.md)
*   [`tf.zeros_like`](../../api_docs/python/tf/zeros_like.md)
*   [`tf.ones`](../../api_docs/python/tf/ones.md)
*   [`tf.ones_like`](../../api_docs/python/tf/ones_like.md)
*   [`tf.fill`](../../api_docs/python/tf/fill.md)
*   [`tf.constant`](../../api_docs/python/tf/constant.md)

<h2 id="Sequences">Sequences</h2>

*   [`tf.linspace`](../../api_docs/python/tf/lin_space.md)
*   [`tf.range`](../../api_docs/python/tf/range.md)

<h2 id="Random_Tensors">Random Tensors</h2>

TensorFlow has several ops that create random tensors with different
distributions.  The random ops are stateful, and create new random values each
time they are evaluated.

The `seed` keyword argument in these functions acts in conjunction with
the graph-level random seed. Changing either the graph-level seed using
[`tf.set_random_seed`](../../api_docs/python/tf/set_random_seed.md) or the
op-level seed will change the underlying seed of these operations. Setting
neither graph-level nor op-level seed, results in a random seed for all
operations.
See [`tf.set_random_seed`](../../api_docs/python/tf/set_random_seed.md)
for details on the interaction between operation-level and graph-level random
seeds.

### Examples:

```python
# Create a tensor of shape [2, 3] consisting of random normal values, with mean
# -1 and standard deviation 4.
norm = tf.random_normal([2, 3], mean=-1, stddev=4)

# Shuffle the first dimension of a tensor
c = tf.constant([[1, 2], [3, 4], [5, 6]])
shuff = tf.random_shuffle(c)

# Each time we run these ops, different results are generated
sess = tf.Session()
print(sess.run(norm))
print(sess.run(norm))

# Set an op-level seed to generate repeatable sequences across sessions.
norm = tf.random_normal([2, 3], seed=1234)
sess = tf.Session()
print(sess.run(norm))
print(sess.run(norm))
sess = tf.Session()
print(sess.run(norm))
print(sess.run(norm))
```

Another common use of random values is the initialization of variables. Also see
the [Variables How To](../../programmers_guide/variables.md).

```python
# Use random uniform values in [0, 1) as the initializer for a variable of shape
# [2, 3]. The default type is float32.
var = tf.Variable(tf.random_uniform([2, 3]), name="var")
init = tf.global_variables_initializer()

sess = tf.Session()
sess.run(init)
print(sess.run(var))
```

*   [`tf.random_normal`](../../api_docs/python/tf/random_normal.md)
*   [`tf.truncated_normal`](../../api_docs/python/tf/truncated_normal.md)
*   [`tf.random_uniform`](../../api_docs/python/tf/random_uniform.md)
*   [`tf.random_shuffle`](../../api_docs/python/tf/random_shuffle.md)
*   [`tf.random_crop`](../../api_docs/python/tf/random_crop.md)
*   [`tf.multinomial`](../../api_docs/python/tf/multinomial.md)
*   [`tf.random_gamma`](../../api_docs/python/tf/random_gamma.md)
*   [`tf.set_random_seed`](../../api_docs/python/tf/set_random_seed.md)
