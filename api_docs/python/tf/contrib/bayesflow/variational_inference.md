<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.bayesflow.variational_inference" />
</div>

# Module: tf.contrib.bayesflow.variational_inference



Defined in [`tensorflow/contrib/bayesflow/python/ops/variational_inference.py`](https://www.tensorflow.org/code/tensorflow/contrib/bayesflow/python/ops/variational_inference.py).

Variational inference.

See the ${@python/contrib.bayesflow.variational_inference} guide.

## Classes

[`class ELBOForms`](../../../tf/contrib/bayesflow/variational_inference/ELBOForms.md): Constants to control the `elbo` calculation.

## Functions

[`elbo(...)`](../../../tf/contrib/bayesflow/variational_inference/elbo.md): Evidence Lower BOund. `log p(x) >= ELBO`.

[`elbo_with_log_joint(...)`](../../../tf/contrib/bayesflow/variational_inference/elbo_with_log_joint.md): Evidence Lower BOund. `log p(x) >= ELBO`.

[`register_prior(...)`](../../../tf/contrib/bayesflow/variational_inference/register_prior.md): Associate a variational `StochasticTensor` with a `Distribution` prior.

