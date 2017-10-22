<!-- DO NOT EDIT! Automatically generated file. -->
# Statistical Distributions (contrib)
[TOC]

Classes representing statistical distributions and ops for working with them.

<h2 id="Classes_for_statistical_distributions">Classes for statistical distributions</h2>

Classes that represent batches of statistical distributions.  Each class is
initialized with parameters that define the distributions.

<h2 id="Base_classes">Base classes</h2>

*   [`tf.contrib.distributions.ReparameterizationType`](../../api_docs/python/tf/distributions/ReparameterizationType.md)
*   [`tf.contrib.distributions.Distribution`](../../api_docs/python/tf/distributions/Distribution.md)

<h2 id="Univariate_scalar_distributions">Univariate (scalar) distributions</h2>

*   [`tf.contrib.distributions.Binomial`](../../api_docs/python/tf/contrib/distributions/Binomial.md)
*   [`tf.contrib.distributions.Bernoulli`](../../api_docs/python/tf/distributions/Bernoulli.md)
*   [`tf.contrib.distributions.BernoulliWithSigmoidProbs`](../../api_docs/python/tf/contrib/distributions/BernoulliWithSigmoidProbs.md)
*   [`tf.contrib.distributions.Beta`](../../api_docs/python/tf/distributions/Beta.md)
*   [`tf.contrib.distributions.Categorical`](../../api_docs/python/tf/distributions/Categorical.md)
*   [`tf.contrib.distributions.Chi2`](../../api_docs/python/tf/contrib/distributions/Chi2.md)
*   [`tf.contrib.distributions.Chi2WithAbsDf`](../../api_docs/python/tf/contrib/distributions/Chi2WithAbsDf.md)
*   [`tf.contrib.distributions.Exponential`](../../api_docs/python/tf/distributions/Exponential.md)
*   [`tf.contrib.distributions.Gamma`](../../api_docs/python/tf/distributions/Gamma.md)
*   [`tf.contrib.distributions.InverseGamma`](../../api_docs/python/tf/contrib/distributions/InverseGamma.md)
*   [`tf.contrib.distributions.Laplace`](../../api_docs/python/tf/distributions/Laplace.md)
*   [`tf.contrib.distributions.LaplaceWithSoftplusScale`](../../api_docs/python/tf/contrib/distributions/LaplaceWithSoftplusScale.md)
*   [`tf.contrib.distributions.Normal`](../../api_docs/python/tf/distributions/Normal.md)
*   [`tf.contrib.distributions.NormalWithSoftplusScale`](../../api_docs/python/tf/contrib/distributions/NormalWithSoftplusScale.md)
*   [`tf.contrib.distributions.Poisson`](../../api_docs/python/tf/contrib/distributions/Poisson.md)
*   [`tf.contrib.distributions.StudentT`](../../api_docs/python/tf/distributions/StudentT.md)
*   [`tf.contrib.distributions.StudentTWithAbsDfSoftplusScale`](../../api_docs/python/tf/contrib/distributions/StudentTWithAbsDfSoftplusScale.md)
*   [`tf.contrib.distributions.Uniform`](../../api_docs/python/tf/distributions/Uniform.md)

<h2 id="Multivariate_distributions">Multivariate distributions</h2>

### Multivariate normal

*   [`tf.contrib.distributions.MultivariateNormalDiag`](../../api_docs/python/tf/contrib/distributions/MultivariateNormalDiag.md)
*   [`tf.contrib.distributions.MultivariateNormalTriL`](../../api_docs/python/tf/contrib/distributions/MultivariateNormalTriL.md)
*   [`tf.contrib.distributions.MultivariateNormalDiagPlusLowRank`](../../api_docs/python/tf/contrib/distributions/MultivariateNormalDiagPlusLowRank.md)
*   [`tf.contrib.distributions.MultivariateNormalDiagWithSoftplusScale`](../../api_docs/python/tf/contrib/distributions/MultivariateNormalDiagWithSoftplusScale.md)

### Other multivariate distributions

*   [`tf.contrib.distributions.Dirichlet`](../../api_docs/python/tf/distributions/Dirichlet.md)
*   [`tf.contrib.distributions.DirichletMultinomial`](../../api_docs/python/tf/distributions/DirichletMultinomial.md)
*   [`tf.contrib.distributions.Multinomial`](../../api_docs/python/tf/distributions/Multinomial.md)
*   [`tf.contrib.distributions.WishartCholesky`](../../api_docs/python/tf/contrib/distributions/WishartCholesky.md)
*   [`tf.contrib.distributions.WishartFull`](../../api_docs/python/tf/contrib/distributions/WishartFull.md)

### Multivariate Utilities

*   [`tf.contrib.distributions.matrix_diag_transform`](../../api_docs/python/tf/contrib/distributions/matrix_diag_transform.md)

<h2 id="Transformed_distributions">Transformed distributions</h2>

*   [`tf.contrib.distributions.TransformedDistribution`](../../api_docs/python/tf/contrib/distributions/TransformedDistribution.md)
*   [`tf.contrib.distributions.QuantizedDistribution`](../../api_docs/python/tf/contrib/distributions/QuantizedDistribution.md)

<h2 id="Mixture_Models">Mixture Models</h2>

*   [`tf.contrib.distributions.Mixture`](../../api_docs/python/tf/contrib/distributions/Mixture.md)

<h2 id="Posterior_inference_with_conjugate_priors">Posterior inference with conjugate priors</h2>

Functions that transform conjugate prior/likelihood pairs to distributions
representing the posterior or posterior predictive.

<h2 id="Normal_likelihood_with_conjugate_prior">Normal likelihood with conjugate prior</h2>

*   [`tf.contrib.distributions.normal_conjugates_known_scale_posterior`](../../api_docs/python/tf/contrib/distributions/normal_conjugates_known_scale_posterior.md)
*   [`tf.contrib.distributions.normal_conjugates_known_scale_predictive`](../../api_docs/python/tf/contrib/distributions/normal_conjugates_known_scale_predictive.md)

<h2 id="Kullback_Leibler_Divergence">Kullback-Leibler Divergence</h2>

*   [`tf.contrib.distributions.kl_divergence`](../../api_docs/python/tf/distributions/kl_divergence.md)
*   [`tf.contrib.distributions.RegisterKL`](../../api_docs/python/tf/distributions/RegisterKL.md)

<h2 id="Utilities">Utilities</h2>

*   [`tf.contrib.distributions.softplus_inverse`](../../api_docs/python/tf/contrib/distributions/softplus_inverse.md)
