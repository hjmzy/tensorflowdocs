<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distributions" />
<meta itemprop="property" content="FULLY_REPARAMETERIZED"/>
<meta itemprop="property" content="NOT_REPARAMETERIZED"/>
</div>

# Module: tf.distributions



Defined in [`tensorflow/python/ops/distributions/distributions.py`](https://www.tensorflow.org/code/tensorflow/python/ops/distributions/distributions.py).

Core module for TensorFlow distribution objects and helpers.

## Modules

[`bijectors`](../tf/distributions/bijectors.md) module: Core module for TensorFlow distribution bijectors.

## Classes

[`class Bernoulli`](../tf/distributions/Bernoulli.md): Bernoulli distribution.

[`class Beta`](../tf/distributions/Beta.md): Beta distribution.

[`class Categorical`](../tf/distributions/Categorical.md): Categorical distribution.

[`class Dirichlet`](../tf/distributions/Dirichlet.md): Dirichlet distribution.

[`class DirichletMultinomial`](../tf/distributions/DirichletMultinomial.md): Dirichlet-Multinomial compound distribution.

[`class Distribution`](../tf/distributions/Distribution.md): A generic probability distribution base class.

[`class Exponential`](../tf/distributions/Exponential.md): Exponential distribution.

[`class Gamma`](../tf/distributions/Gamma.md): Gamma distribution.

[`class Laplace`](../tf/distributions/Laplace.md): The Laplace distribution with location `loc` and `scale` parameters.

[`class Multinomial`](../tf/distributions/Multinomial.md): Multinomial distribution.

[`class Normal`](../tf/distributions/Normal.md): The Normal distribution with location `loc` and `scale` parameters.

[`class RegisterKL`](../tf/distributions/RegisterKL.md): Decorator to register a KL divergence implementation function.

[`class ReparameterizationType`](../tf/distributions/ReparameterizationType.md): Instances of this class represent how sampling is reparameterized.

[`class StudentT`](../tf/distributions/StudentT.md): Student's t-distribution.

[`class Uniform`](../tf/distributions/Uniform.md): Uniform distribution with `low` and `high` parameters.

## Functions

[`kl_divergence(...)`](../tf/distributions/kl_divergence.md): Get the KL-divergence KL(distribution_a || distribution_b).

## Other Members

`FULLY_REPARAMETERIZED`

`NOT_REPARAMETERIZED`

