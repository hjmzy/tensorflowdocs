<!-- DO NOT EDIT! Automatically generated file. -->
# Random variable transformations (contrib)
[TOC]

Bijector Ops.

An API for invertible, differentiable transformations of random variables.

<h2 id="Background">Background</h2>

Differentiable, bijective transformations of continuous random variables alter
the calculations made in the cumulative/probability distribution functions and
sample function.  This module provides a standard interface for making these
manipulations.

For more details and examples, see the `Bijector` docstring.

To apply a `Bijector`, use `distributions.TransformedDistribution`.

<h2 id="Bijectors">Bijectors</h2>

*   [`tf.contrib.distributions.bijectors.Affine`](../../api_docs/python/tf/contrib/distributions/bijectors/Affine.md)
*   [`tf.contrib.distributions.bijectors.AffineLinearOperator`](../../api_docs/python/tf/contrib/distributions/bijectors/AffineLinearOperator.md)
*   [`tf.contrib.distributions.bijectors.Bijector`](../../api_docs/python/tf/distributions/bijectors/Bijector.md)
*   [`tf.contrib.distributions.bijectors.Chain`](../../api_docs/python/tf/contrib/distributions/bijectors/Chain.md)
*   [`tf.contrib.distributions.bijectors.CholeskyOuterProduct`](../../api_docs/python/tf/contrib/distributions/bijectors/CholeskyOuterProduct.md)
*   [`tf.contrib.distributions.bijectors.Exp`](../../api_docs/python/tf/contrib/distributions/bijectors/Exp.md)
*   [`tf.contrib.distributions.bijectors.Identity`](../../api_docs/python/tf/distributions/bijectors/Identity.md)
*   [`tf.contrib.distributions.bijectors.Inline`](../../api_docs/python/tf/contrib/distributions/bijectors/Inline.md)
*   [`tf.contrib.distributions.bijectors.Invert`](../../api_docs/python/tf/contrib/distributions/bijectors/Invert.md)
*   [`tf.contrib.distributions.bijectors.PowerTransform`](../../api_docs/python/tf/contrib/distributions/bijectors/PowerTransform.md)
*   [`tf.contrib.distributions.bijectors.SigmoidCentered`](../../api_docs/python/tf/contrib/distributions/bijectors/SigmoidCentered.md)
*   [`tf.contrib.distributions.bijectors.SoftmaxCentered`](../../api_docs/python/tf/contrib/distributions/bijectors/SoftmaxCentered.md)
*   [`tf.contrib.distributions.bijectors.Softplus`](../../api_docs/python/tf/contrib/distributions/bijectors/Softplus.md)
