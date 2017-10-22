<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.metrics" />
</div>

# Module: tf.metrics



Defined in [`tensorflow/python/ops/metrics.py`](https://www.tensorflow.org/code/tensorflow/python/ops/metrics.py).

Evaluation-related metrics.


## Functions

[`accuracy(...)`](../tf/metrics/accuracy.md): Calculates how often `predictions` matches `labels`.

[`auc(...)`](../tf/metrics/auc.md): Computes the approximate AUC via a Riemann sum.

[`false_negatives(...)`](../tf/metrics/false_negatives.md): Computes the total number of false negatives.

[`false_negatives_at_thresholds(...)`](../tf/metrics/false_negatives_at_thresholds.md): Computes false negatives at provided threshold values.

[`false_positives(...)`](../tf/metrics/false_positives.md): Sum the weights of false positives.

[`false_positives_at_thresholds(...)`](../tf/metrics/false_positives_at_thresholds.md): Computes false positives at provided threshold values.

[`mean(...)`](../tf/metrics/mean.md): Computes the (weighted) mean of the given values.

[`mean_absolute_error(...)`](../tf/metrics/mean_absolute_error.md): Computes the mean absolute error between the labels and predictions.

[`mean_cosine_distance(...)`](../tf/metrics/mean_cosine_distance.md): Computes the cosine distance between the labels and predictions.

[`mean_iou(...)`](../tf/metrics/mean_iou.md): Calculate per-step mean Intersection-Over-Union (mIOU).

[`mean_per_class_accuracy(...)`](../tf/metrics/mean_per_class_accuracy.md): Calculates the mean of the per-class accuracies.

[`mean_relative_error(...)`](../tf/metrics/mean_relative_error.md): Computes the mean relative error by normalizing with the given values.

[`mean_squared_error(...)`](../tf/metrics/mean_squared_error.md): Computes the mean squared error between the labels and predictions.

[`mean_tensor(...)`](../tf/metrics/mean_tensor.md): Computes the element-wise (weighted) mean of the given tensors.

[`percentage_below(...)`](../tf/metrics/percentage_below.md): Computes the percentage of values less than the given threshold.

[`precision(...)`](../tf/metrics/precision.md): Computes the precision of the predictions with respect to the labels.

[`precision_at_thresholds(...)`](../tf/metrics/precision_at_thresholds.md): Computes precision values for different `thresholds` on `predictions`.

[`recall(...)`](../tf/metrics/recall.md): Computes the recall of the predictions with respect to the labels.

[`recall_at_k(...)`](../tf/metrics/recall_at_k.md): Computes recall@k of the predictions with respect to sparse labels.

[`recall_at_thresholds(...)`](../tf/metrics/recall_at_thresholds.md): Computes various recall values for different `thresholds` on `predictions`.

[`root_mean_squared_error(...)`](../tf/metrics/root_mean_squared_error.md): Computes the root mean squared error between the labels and predictions.

[`sensitivity_at_specificity(...)`](../tf/metrics/sensitivity_at_specificity.md): Computes the specificity at a given sensitivity.

[`sparse_average_precision_at_k(...)`](../tf/metrics/sparse_average_precision_at_k.md): Computes average precision@k of predictions with respect to sparse labels.

[`sparse_precision_at_k(...)`](../tf/metrics/sparse_precision_at_k.md): Computes precision@k of the predictions with respect to sparse labels.

[`specificity_at_sensitivity(...)`](../tf/metrics/specificity_at_sensitivity.md): Computes the specificity at a given sensitivity.

[`true_negatives_at_thresholds(...)`](../tf/metrics/true_negatives_at_thresholds.md): Computes true negatives at provided threshold values.

[`true_positives(...)`](../tf/metrics/true_positives.md): Sum the weights of true_positives.

[`true_positives_at_thresholds(...)`](../tf/metrics/true_positives_at_thresholds.md): Computes true positives at provided threshold values.

