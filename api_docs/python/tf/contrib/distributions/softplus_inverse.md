<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.distributions.softplus_inverse" />
</div>

# tf.contrib.distributions.softplus_inverse

``` python
softplus_inverse(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/distributions/util.py`](https://www.tensorflow.org/code/tensorflow/python/ops/distributions/util.py).

See the guide: [Statistical Distributions (contrib) > Utilities](../../../../../api_guides/python/contrib.distributions.md#Utilities)

Computes the inverse softplus, i.e., x = softplus_inverse(softplus(x)).

Mathematically this op is equivalent to:

```none
softplus_inverse = log(exp(x) - 1.)
```

#### Args:

* <b>`x`</b>: `Tensor`. Non-negative (not enforced), floating-point.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

`Tensor`. Has the same type/shape as input `x`.