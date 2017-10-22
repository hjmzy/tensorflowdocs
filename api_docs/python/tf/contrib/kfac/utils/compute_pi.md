<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.utils.compute_pi" />
</div>

# tf.contrib.kfac.utils.compute_pi

``` python
compute_pi(
    left_factor,
    right_factor
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/utils.py).

Computes the scalar constant pi for Tikhonov regularization/damping.

pi = sqrt( (trace(A) / dim(A)) / (trace(B) / dim(B)) )
See section 6.3 of https://arxiv.org/pdf/1503.05671.pdf for details.

#### Args:

* <b>`left_factor`</b>: The left Kronecker factor Tensor.
* <b>`right_factor`</b>: The right Kronecker factor Tensor.


#### Returns:

The computed scalar constant pi for these Kronecker Factors (as a Tensor).