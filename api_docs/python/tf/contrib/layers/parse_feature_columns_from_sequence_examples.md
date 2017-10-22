<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.parse_feature_columns_from_sequence_examples" />
</div>

# tf.contrib.layers.parse_feature_columns_from_sequence_examples

``` python
parse_feature_columns_from_sequence_examples(
    serialized,
    context_feature_columns,
    sequence_feature_columns,
    name=None,
    example_name=None
)
```



Defined in [`tensorflow/contrib/layers/python/layers/feature_column_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/feature_column_ops.py).

See the guide: [Layers (contrib) > Feature columns](../../../../../api_guides/python/contrib.layers.md#Feature_columns)

Parses tf.SequenceExamples to extract tensors for given `FeatureColumn`s.

#### Args:

* <b>`serialized`</b>: A scalar (0-D Tensor) of type string, a single serialized
    `SequenceExample` proto.
* <b>`context_feature_columns`</b>: An iterable containing the feature columns for
    context features. All items should be instances of classes derived from
    `_FeatureColumn`. Can be `None`.
* <b>`sequence_feature_columns`</b>: An iterable containing the feature columns for
    sequence features. All items should be instances of classes derived from
    `_FeatureColumn`. Can be `None`.
* <b>`name`</b>: A name for this operation (optional).
* <b>`example_name`</b>: A scalar (0-D Tensor) of type string (optional), the names of
    the serialized proto.


#### Returns:

A tuple consisting of:
* <b>`context_features`</b>: a dict mapping `FeatureColumns` from
    `context_feature_columns` to their parsed `Tensors`/`SparseTensor`s.
* <b>`sequence_features`</b>: a dict mapping `FeatureColumns` from
    `sequence_feature_columns` to their parsed `Tensors`/`SparseTensor`s.