<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.infogan_model" />
</div>

# tf.contrib.gan.infogan_model

``` python
infogan_model(
    generator_fn,
    discriminator_fn,
    real_data,
    unstructured_generator_inputs,
    structured_generator_inputs,
    generator_scope='Generator',
    discriminator_scope='Discriminator'
)
```



Defined in [`tensorflow/contrib/gan/python/train.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/train.py).

Returns an InfoGAN model outputs and variables.

See https://arxiv.org/abs/1606.03657 for more details.

#### Args:

* <b>`generator_fn`</b>: A python lambda that takes a list of Tensors as inputs and
    returns the outputs of the GAN generator.
* <b>`discriminator_fn`</b>: A python lambda that takes `real_data`/`generated data`
    and `generator_inputs`. Outputs a 2-tuple of (logits, distribution_list).
    `logits` are in the range [-inf, inf], and `distribution_list` is a list
    of Tensorflow distributions representing the predicted noise distribution
    of the ith structure noise.
* <b>`real_data`</b>: A Tensor representing the real data.
* <b>`unstructured_generator_inputs`</b>: A list of Tensors to the generator.
    These tensors represent the unstructured noise or conditioning.
* <b>`structured_generator_inputs`</b>: A list of Tensors to the generator.
    These tensors must have high mutual information with the recognizer.
* <b>`generator_scope`</b>: Optional generator variable scope. Useful if you want to
    reuse a subgraph that has already been created.
* <b>`discriminator_scope`</b>: Optional discriminator variable scope. Useful if you
    want to reuse a subgraph that has already been created.


#### Returns:

An InfoGANModel namedtuple.


#### Raises:

* <b>`ValueError`</b>: If the generator outputs a Tensor that isn't the same shape as
    `real_data`.
* <b>`ValueError`</b>: If the discriminator output is malformed.