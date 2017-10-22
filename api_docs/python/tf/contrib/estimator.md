<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.estimator" />
</div>

# Module: tf.contrib.estimator



Defined in [`tensorflow/contrib/estimator/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/estimator/__init__.py).

Experimental utilities re:tf.estimator.*.

## Classes

[`class DNNEstimator`](../../tf/contrib/estimator/DNNEstimator.md): An estimator for TensorFlow DNN models with user-specified head.

## Functions

[`add_metrics(...)`](../../tf/contrib/estimator/add_metrics.md): Creates a new ${tf.estimator.Estimator} which has given metrics.

[`binary_classification_head(...)`](../../tf/contrib/estimator/binary_classification_head.md): Creates a `_Head` for single label binary classification.

[`call_logit_fn(...)`](../../tf/contrib/estimator/call_logit_fn.md): Calls logit_fn.

[`clip_gradients_by_norm(...)`](../../tf/contrib/estimator/clip_gradients_by_norm.md): Returns an optimizer which clips gradients before appliying them.

[`dnn_logit_fn_builder(...)`](../../tf/contrib/estimator/dnn_logit_fn_builder.md): Function builder for a dnn logit_fn.

[`forward_features(...)`](../../tf/contrib/estimator/forward_features.md): Forward features to predictions dictionary.

[`linear_logit_fn_builder(...)`](../../tf/contrib/estimator/linear_logit_fn_builder.md): Function builder for a linear logit_fn.

[`multi_class_head(...)`](../../tf/contrib/estimator/multi_class_head.md): Creates a `_Head` for multi class classification.

[`multi_head(...)`](../../tf/contrib/estimator/multi_head.md): Creates a `_Head` for multi-objective learning.

[`multi_label_head(...)`](../../tf/contrib/estimator/multi_label_head.md): Creates a `_Head` for multi-label classification.

[`regression_head(...)`](../../tf/contrib/estimator/regression_head.md): Creates a `_Head` for regression using the mean squared loss.

