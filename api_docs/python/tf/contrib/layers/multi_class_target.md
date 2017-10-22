<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.multi_class_target" />
</div>

# tf.contrib.layers.multi_class_target

``` python
multi_class_target(
    n_classes,
    label_name=None,
    weight_column_name=None
)
```



Defined in [`tensorflow/contrib/layers/python/layers/target_column.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/target_column.py).

See the guide: [Layers (contrib) > Feature columns](../../../../../api_guides/python/contrib.layers.md#Feature_columns)

Creates a _TargetColumn for multi class single label classification. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2016-11-12.
Instructions for updating:
This file will be removed after the deprecation date.Please switch to third_party/tensorflow/contrib/learn/python/learn/estimators/head.py

The target column uses softmax cross entropy loss.

#### Args:

* <b>`n_classes`</b>: Integer, number of classes, must be >= 2
* <b>`label_name`</b>: String, name of the key in label dict. Can be null if label
      is a tensor (single headed models).
* <b>`weight_column_name`</b>: A string defining feature column name representing
    weights. It is used to down weight or boost examples during training. It
    will be multiplied by the loss of the example.


#### Returns:

An instance of _MultiClassTargetColumn.


#### Raises:

* <b>`ValueError`</b>: if n_classes is < 2