<!-- DO NOT EDIT! Automatically generated file. -->
# BayesFlow Stochastic Tensors (contrib)
[TOC]

Classes and helper functions for creating Stochastic Tensors.

`StochasticTensor` objects wrap `Distribution` objects.  Their
values may be samples from the underlying distribution, or the distribution
mean (as governed by `value_type`).  These objects provide a `loss`
method for use when sampling from a non-reparameterized distribution.
The `loss`method is used in conjunction with `stochastic_graph.surrogate_loss`
to produce a single differentiable loss in stochastic graphs having
both continuous and discrete stochastic nodes.

<h2 id="Stochastic_Tensor_Classes">Stochastic Tensor Classes</h2>

*   [`tf.contrib.bayesflow.stochastic_tensor.BaseStochasticTensor`](../../api_docs/python/tf/contrib/bayesflow/stochastic_tensor/BaseStochasticTensor.md)
*   [`tf.contrib.bayesflow.stochastic_tensor.StochasticTensor`](../../api_docs/python/tf/contrib/bayesflow/stochastic_tensor/StochasticTensor.md)

<h2 id="Stochastic_Tensor_Value_Types">Stochastic Tensor Value Types</h2>

*   [`tf.contrib.bayesflow.stochastic_tensor.MeanValue`](../../api_docs/python/tf/contrib/bayesflow/stochastic_tensor/MeanValue.md)
*   [`tf.contrib.bayesflow.stochastic_tensor.SampleValue`](../../api_docs/python/tf/contrib/bayesflow/stochastic_tensor/SampleValue.md)
*   [`tf.contrib.bayesflow.stochastic_tensor.value_type`](../../api_docs/python/tf/contrib/bayesflow/stochastic_tensor/value_type.md)
*   [`tf.contrib.bayesflow.stochastic_tensor.get_current_value_type`](../../api_docs/python/tf/contrib/bayesflow/stochastic_tensor/get_current_value_type.md)
