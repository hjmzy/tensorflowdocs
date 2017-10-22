<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.bayesflow.stochastic_tensor" />
</div>

# Module: tf.contrib.bayesflow.stochastic_tensor



Defined in [`tensorflow/contrib/bayesflow/python/ops/stochastic_tensor.py`](https://www.tensorflow.org/code/tensorflow/contrib/bayesflow/python/ops/stochastic_tensor.py).

Support for creating Stochastic Tensors.

See the [BayesFlow Stochastic Tensors (contrib)](../../../../../api_guides/python/contrib.bayesflow.stochastic_tensor.md) guide.


## Classes

[`class BaseStochasticTensor`](../../../tf/contrib/bayesflow/stochastic_tensor/BaseStochasticTensor.md): Base Class for Tensor-like objects that emit stochastic values.

[`class MeanValue`](../../../tf/contrib/bayesflow/stochastic_tensor/MeanValue.md)

[`class ObservedStochasticTensor`](../../../tf/contrib/bayesflow/stochastic_tensor/ObservedStochasticTensor.md): A StochasticTensor with an observed value.

[`class SampleValue`](../../../tf/contrib/bayesflow/stochastic_tensor/SampleValue.md): Draw samples, possibly adding new outer dimensions along the way.

[`class StochasticTensor`](../../../tf/contrib/bayesflow/stochastic_tensor/StochasticTensor.md): StochasticTensor is a BaseStochasticTensor backed by a distribution.

## Functions

[`get_current_value_type(...)`](../../../tf/contrib/bayesflow/stochastic_tensor/get_current_value_type.md)

[`value_type(...)`](../../../tf/contrib/bayesflow/stochastic_tensor/value_type.md): Creates a value type context for any StochasticTensor created within.

