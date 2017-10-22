<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.regression_target" />
</div>

# tf.contrib.layers.regression_target

``` python
regression_target(
    label_name=None,
    weight_column_name=None,
    label_dimension=1
)
```



Defined in [`tensorflow/contrib/layers/python/layers/target_column.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/target_column.py).

Creates a _TargetColumn for linear regression. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2016-11-12.
Instructions for updating:
This file will be removed after the deprecation date.Please switch to third_party/tensorflow/contrib/learn/python/learn/estimators/head.py

#### Args:

* <b>`label_name`</b>: String, name of the key in label dict. Can be null if label
      is a tensor (single headed models).
* <b>`weight_column_name`</b>: A string defining feature column name representing
    weights. It is used to down weight or boost examples during training. It
    will be multiplied by the loss of the example.
* <b>`label_dimension`</b>: dimension of the target for multilabels.


#### Returns:

An instance of _TargetColumn