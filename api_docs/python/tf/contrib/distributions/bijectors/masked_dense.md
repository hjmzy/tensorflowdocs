<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distributions.bijectors.masked_dense" />
</div>

# tf.contrib.distributions.bijectors.masked_dense

``` python
masked_dense(
    inputs,
    units,
    num_blocks=None,
    exclusive=False,
    kernel_initializer=None,
    reuse=None,
    name=None,
    *args,
    **kwargs
)
```



Defined in [`tensorflow/contrib/distributions/python/ops/bijectors/masked_autoregressive_impl.py`](https://www.tensorflow.org/code/tensorflow/contrib/distributions/python/ops/bijectors/masked_autoregressive_impl.py).

A autoregressively masked dense layer. Analogous to `tf.layers.dense`.

See [1] for detailed explanation.

[1]: "MADE: Masked Autoencoder for Distribution Estimation."
     Mathieu Germain, Karol Gregor, Iain Murray, Hugo Larochelle. ICML. 2015.
     https://arxiv.org/abs/1502.03509

#### Arguments:

* <b>`inputs`</b>: Tensor input.
* <b>`units`</b>: Python `int` scalar representing the dimensionality of the output
    space.
* <b>`num_blocks`</b>: Python `int` scalar representing the number of blocks for the
    MADE masks.
* <b>`exclusive`</b>: Python `bool` scalar representing whether to zero the diagonal of
    the mask, used for the first layer of a MADE.
* <b>`kernel_initializer`</b>: Initializer function for the weight matrix.
    If `None` (default), weights are initialized using the
    `tf.glorot_random_initializer`.
* <b>`reuse`</b>: Python `bool` scalar representing whether to reuse the weights of a
    previous layer by the same name.
* <b>`name`</b>: Python `str` used to describe ops managed by this function.
* <b>`*args`</b>: `tf.layers.dense` arguments.
* <b>`**kwargs`</b>: `tf.layers.dense` keyword arguments.


#### Returns:

Output tensor.


#### Raises:

* <b>`NotImplementedError`</b>: if rightmost dimension of `inputs` is unknown prior to
    graph execution.