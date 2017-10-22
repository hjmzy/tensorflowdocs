<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.estimator.linear_logit_fn_builder" />
</div>

# tf.contrib.estimator.linear_logit_fn_builder

``` python
linear_logit_fn_builder(
    units,
    feature_columns
)
```



Defined in [`tensorflow/python/estimator/canned/linear.py`](https://www.tensorflow.org/code/tensorflow/python/estimator/canned/linear.py).

Function builder for a linear logit_fn.

#### Args:

* <b>`units`</b>: An int indicating the dimension of the logit layer.
* <b>`feature_columns`</b>: An iterable containing all the feature columns used by
    the model.


#### Returns:

A logit_fn (see below).