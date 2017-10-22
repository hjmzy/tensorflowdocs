<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.seq2seq.safe_cumprod" />
</div>

# tf.contrib.seq2seq.safe_cumprod

``` python
safe_cumprod(
    x,
    *args,
    **kwargs
)
```



Defined in [`tensorflow/contrib/seq2seq/python/ops/attention_wrapper.py`](https://www.tensorflow.org/code/tensorflow/contrib/seq2seq/python/ops/attention_wrapper.py).

Computes cumprod of x in logspace using cumsum to avoid underflow.

The cumprod function and its gradient can result in numerical instabilities
when its argument has very small and/or zero values.  As long as the argument
is all positive, we can instead compute the cumulative product as
exp(cumsum(log(x))).  This function can be called identically to tf.cumprod.

#### Args:

* <b>`x`</b>: Tensor to take the cumulative product of.
* <b>`*args`</b>: Passed on to cumsum; these are identical to those in cumprod.
* <b>`**kwargs`</b>: Passed on to cumsum; these are identical to those in cumprod.

#### Returns:

Cumulative product of x.