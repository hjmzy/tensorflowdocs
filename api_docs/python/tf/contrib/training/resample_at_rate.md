<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.training.resample_at_rate" />
</div>

# tf.contrib.training.resample_at_rate

``` python
resample_at_rate(
    inputs,
    rates,
    scope=None,
    seed=None,
    back_prop=False
)
```



Defined in [`tensorflow/contrib/training/python/training/resample.py`](https://www.tensorflow.org/code/tensorflow/contrib/training/python/training/resample.py).

See the guide: [Training (contrib) > Online data resampling](../../../../../api_guides/python/contrib.training.md#Online_data_resampling)

Given `inputs` tensors, stochastically resamples each at a given rate.

For example, if the inputs are `[[a1, a2], [b1, b2]]` and the rates
tensor contains `[3, 1]`, then the return value may look like `[[a1,
a2, a1, a1], [b1, b2, b1, b1]]`. However, many other outputs are
possible, since this is stochastic -- averaged over many repeated
calls, each set of inputs should appear in the output `rate` times
the number of invocations.

#### Args:

* <b>`inputs`</b>: A list of tensors, each of which has a shape of `[batch_size, ...]`
* <b>`rates`</b>: A tensor of shape `[batch_size]` contiaining the resampling rates
     for each input.
* <b>`scope`</b>: Scope for the op.
* <b>`seed`</b>: Random seed to use.
* <b>`back_prop`</b>: Whether to allow back-propagation through this op.


#### Returns:

Selections from the input tensors.