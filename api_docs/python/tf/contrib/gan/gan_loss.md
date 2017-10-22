<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.gan_loss" />
</div>

# tf.contrib.gan.gan_loss

``` python
gan_loss(
    model,
    generator_loss_fn=tf.contrib.gan.losses.wasserstein_generator_loss,
    discriminator_loss_fn=tf.contrib.gan.losses.wasserstein_discriminator_loss,
    gradient_penalty_weight=None,
    gradient_penalty_epsilon=1e-10,
    mutual_information_penalty_weight=None,
    aux_cond_generator_weight=None,
    aux_cond_discriminator_weight=None,
    add_summaries=True
)
```



Defined in [`tensorflow/contrib/gan/python/train.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/train.py).

Returns losses necessary to train generator and discriminator.

#### Args:

* <b>`model`</b>: A GANModel tuple.
* <b>`generator_loss_fn`</b>: The loss function on the generator. Takes a GANModel
    tuple.
* <b>`discriminator_loss_fn`</b>: The loss function on the discriminator. Takes a
    GANModel tuple.
* <b>`gradient_penalty_weight`</b>: If not `None`, must be a non-negative Python number
    or Tensor indicating how much to weight the gradient penalty. See
    https://arxiv.org/pdf/1704.00028.pdf for more details.
* <b>`gradient_penalty_epsilon`</b>: If `gradient_penalty_weight` is not None, the
    small positive value used by the gradient penalty function for numerical
    stability. Note some applications will need to increase this value to
    avoid NaNs.
* <b>`mutual_information_penalty_weight`</b>: If not `None`, must be a non-negative
    Python number or Tensor indicating how much to weight the mutual
    information penalty. See https://arxiv.org/abs/1606.03657 for more
    details.
* <b>`aux_cond_generator_weight`</b>: If not None: add a classification loss as in
    https://arxiv.org/abs/1610.09585
* <b>`aux_cond_discriminator_weight`</b>: If not None: add a classification loss as in
    https://arxiv.org/abs/1610.09585
* <b>`add_summaries`</b>: Whether or not to add summaries for the losses.


#### Returns:

A GANLoss 2-tuple of (generator_loss, discriminator_loss). Includes
regularization losses.


#### Raises:

* <b>`ValueError`</b>: If any of the auxiliary loss weights is provided and negative.
* <b>`ValueError`</b>: If `mutual_information_penalty_weight` is provided, but the
    `model` isn't an `InfoGANModel`.