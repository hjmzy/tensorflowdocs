<!-- DO NOT EDIT! Automatically generated file. -->
# Layers (contrib)
[TOC]

Ops for building neural network layers, regularizers, summaries, etc.

<h2 id="Higher_level_ops_for_building_neural_network_layers">Higher level ops for building neural network layers</h2>

This package provides several ops that take care of creating variables that are
used internally in a consistent way and provide the building blocks for many
common machine learning algorithms.

*   [`tf.contrib.layers.avg_pool2d`](../../api_docs/python/tf/contrib/layers/avg_pool2d.md)
*   [`tf.contrib.layers.batch_norm`](../../api_docs/python/tf/contrib/layers/batch_norm.md)
*   [`tf.contrib.layers.convolution2d`](../../api_docs/python/tf/contrib/layers/conv2d.md)
*   [`tf.contrib.layers.conv2d_in_plane`](../../api_docs/python/tf/contrib/layers/conv2d_in_plane.md)
*   [`tf.contrib.layers.convolution2d_in_plane`](../../api_docs/python/tf/contrib/layers/conv2d_in_plane.md)
*   [`tf.nn.conv2d_transpose`](../../api_docs/python/tf/nn/conv2d_transpose.md)
*   [`tf.contrib.layers.convolution2d_transpose`](../../api_docs/python/tf/contrib/layers/conv2d_transpose.md)
*   [`tf.nn.dropout`](../../api_docs/python/tf/nn/dropout.md)
*   [`tf.contrib.layers.flatten`](../../api_docs/python/tf/contrib/layers/flatten.md)
*   [`tf.contrib.layers.fully_connected`](../../api_docs/python/tf/contrib/layers/fully_connected.md)
*   [`tf.contrib.layers.layer_norm`](../../api_docs/python/tf/contrib/layers/layer_norm.md)
*   [`tf.contrib.layers.max_pool2d`](../../api_docs/python/tf/contrib/layers/max_pool2d.md)
*   [`tf.contrib.layers.one_hot_encoding`](../../api_docs/python/tf/contrib/layers/one_hot_encoding.md)
*   [`tf.nn.relu`](../../api_docs/python/tf/nn/relu.md)
*   [`tf.nn.relu6`](../../api_docs/python/tf/nn/relu6.md)
*   [`tf.contrib.layers.repeat`](../../api_docs/python/tf/contrib/layers/repeat.md)
*   [`tf.contrib.layers.safe_embedding_lookup_sparse`](../../api_docs/python/tf/contrib/layers/safe_embedding_lookup_sparse.md)
*   [`tf.nn.separable_conv2d`](../../api_docs/python/tf/nn/separable_conv2d.md)
*   [`tf.contrib.layers.separable_convolution2d`](../../api_docs/python/tf/contrib/layers/separable_conv2d.md)
*   [`tf.nn.softmax`](../../api_docs/python/tf/nn/softmax.md)
*   [`tf.stack`](../../api_docs/python/tf/stack.md)
*   [`tf.contrib.layers.unit_norm`](../../api_docs/python/tf/contrib/layers/unit_norm.md)
*   [`tf.contrib.layers.embed_sequence`](../../api_docs/python/tf/contrib/layers/embed_sequence.md)

Aliases for fully_connected which set a default activation function are
available: `relu`, `relu6` and `linear`.

`stack` operation is also available. It builds a stack of layers by applying
a layer repeatedly.

<h2 id="Regularizers">Regularizers</h2>

Regularization can help prevent overfitting. These have the signature
`fn(weights)`. The loss is typically added to
`tf.GraphKeys.REGULARIZATION_LOSSES`.

*   [`tf.contrib.layers.apply_regularization`](../../api_docs/python/tf/contrib/layers/apply_regularization.md)
*   [`tf.contrib.layers.l1_regularizer`](../../api_docs/python/tf/contrib/layers/l1_regularizer.md)
*   [`tf.contrib.layers.l2_regularizer`](../../api_docs/python/tf/contrib/layers/l2_regularizer.md)
*   [`tf.contrib.layers.sum_regularizer`](../../api_docs/python/tf/contrib/layers/sum_regularizer.md)

<h2 id="Initializers">Initializers</h2>

Initializers are used to initialize variables with sensible values given their
size, data type, and purpose.

*   [`tf.contrib.layers.xavier_initializer`](../../api_docs/python/tf/contrib/layers/xavier_initializer.md)
*   [`tf.contrib.layers.xavier_initializer_conv2d`](../../api_docs/python/tf/contrib/layers/xavier_initializer.md)
*   [`tf.contrib.layers.variance_scaling_initializer`](../../api_docs/python/tf/contrib/layers/variance_scaling_initializer.md)

<h2 id="Optimization">Optimization</h2>

Optimize weights given a loss.

*   [`tf.contrib.layers.optimize_loss`](../../api_docs/python/tf/contrib/layers/optimize_loss.md)

<h2 id="Summaries">Summaries</h2>

Helper functions to summarize specific variables or ops.

*   [`tf.contrib.layers.summarize_activation`](../../api_docs/python/tf/contrib/layers/summarize_activation.md)
*   [`tf.contrib.layers.summarize_tensor`](../../api_docs/python/tf/contrib/layers/summarize_tensor.md)
*   [`tf.contrib.layers.summarize_tensors`](../../api_docs/python/tf/contrib/layers/summarize_tensors.md)
*   [`tf.contrib.layers.summarize_collection`](../../api_docs/python/tf/contrib/layers/summarize_collection.md)

The layers module defines convenience functions `summarize_variables`,
`summarize_weights` and `summarize_biases`, which set the `collection` argument
of `summarize_collection` to `VARIABLES`, `WEIGHTS` and `BIASES`, respectively.

*   [`tf.contrib.layers.summarize_activations`](../../api_docs/python/tf/contrib/layers/summarize_activations.md)

<h2 id="Feature_columns">Feature columns</h2>

Feature columns provide a mechanism to map data to a model.

*   [`tf.contrib.layers.bucketized_column`](../../api_docs/python/tf/contrib/layers/bucketized_column.md)
*   [`tf.contrib.layers.check_feature_columns`](../../api_docs/python/tf/contrib/layers/check_feature_columns.md)
*   [`tf.contrib.layers.create_feature_spec_for_parsing`](../../api_docs/python/tf/contrib/layers/create_feature_spec_for_parsing.md)
*   [`tf.contrib.layers.crossed_column`](../../api_docs/python/tf/contrib/layers/crossed_column.md)
*   [`tf.contrib.layers.embedding_column`](../../api_docs/python/tf/contrib/layers/embedding_column.md)
*   [`tf.contrib.layers.scattered_embedding_column`](../../api_docs/python/tf/contrib/layers/scattered_embedding_column.md)
*   [`tf.contrib.layers.input_from_feature_columns`](../../api_docs/python/tf/contrib/layers/input_from_feature_columns.md)
*   [`tf.contrib.layers.joint_weighted_sum_from_feature_columns`](../../api_docs/python/tf/contrib/layers/joint_weighted_sum_from_feature_columns.md)
*   [`tf.contrib.layers.make_place_holder_tensors_for_base_features`](../../api_docs/python/tf/contrib/layers/make_place_holder_tensors_for_base_features.md)
*   [`tf.contrib.layers.multi_class_target`](../../api_docs/python/tf/contrib/layers/multi_class_target.md)
*   [`tf.contrib.layers.one_hot_column`](../../api_docs/python/tf/contrib/layers/one_hot_column.md)
*   [`tf.contrib.layers.parse_feature_columns_from_examples`](../../api_docs/python/tf/contrib/layers/parse_feature_columns_from_examples.md)
*   [`tf.contrib.layers.parse_feature_columns_from_sequence_examples`](../../api_docs/python/tf/contrib/layers/parse_feature_columns_from_sequence_examples.md)
*   [`tf.contrib.layers.real_valued_column`](../../api_docs/python/tf/contrib/layers/real_valued_column.md)
*   [`tf.contrib.layers.shared_embedding_columns`](../../api_docs/python/tf/contrib/layers/shared_embedding_columns.md)
*   [`tf.contrib.layers.sparse_column_with_hash_bucket`](../../api_docs/python/tf/contrib/layers/sparse_column_with_hash_bucket.md)
*   [`tf.contrib.layers.sparse_column_with_integerized_feature`](../../api_docs/python/tf/contrib/layers/sparse_column_with_integerized_feature.md)
*   [`tf.contrib.layers.sparse_column_with_keys`](../../api_docs/python/tf/contrib/layers/sparse_column_with_keys.md)
*   [`tf.contrib.layers.sparse_column_with_vocabulary_file`](../../api_docs/python/tf/contrib/layers/sparse_column_with_vocabulary_file.md)
*   [`tf.contrib.layers.weighted_sparse_column`](../../api_docs/python/tf/contrib/layers/weighted_sparse_column.md)
*   [`tf.contrib.layers.weighted_sum_from_feature_columns`](../../api_docs/python/tf/contrib/layers/weighted_sum_from_feature_columns.md)
*   [`tf.contrib.layers.infer_real_valued_columns`](../../api_docs/python/tf/contrib/layers/infer_real_valued_columns.md)
*   [`tf.contrib.layers.sequence_input_from_feature_columns`](../../api_docs/python/tf/contrib/layers/sequence_input_from_feature_columns.md)
