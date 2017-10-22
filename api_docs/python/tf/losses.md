<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses" />
</div>

# Module: tf.losses



Defined in [`tensorflow/python/ops/losses/losses.py`](https://www.tensorflow.org/code/tensorflow/python/ops/losses/losses.py).

Loss operations for use in neural networks.

Note: All the losses are added to the `GraphKeys.LOSSES` collection by default.


## Classes

[`class Reduction`](../tf/losses/Reduction.md): Types of loss reduction.

## Functions

[`absolute_difference(...)`](../tf/losses/absolute_difference.md): Adds an Absolute Difference loss to the training procedure.

[`add_loss(...)`](../tf/losses/add_loss.md): Adds a externally defined loss to the collection of losses.

[`compute_weighted_loss(...)`](../tf/losses/compute_weighted_loss.md): Computes the weighted loss.

[`cosine_distance(...)`](../tf/losses/cosine_distance.md): Adds a cosine-distance loss to the training procedure. (deprecated arguments)

[`get_losses(...)`](../tf/losses/get_losses.md): Gets the list of losses from the loss_collection.

[`get_regularization_loss(...)`](../tf/losses/get_regularization_loss.md): Gets the total regularization loss.

[`get_regularization_losses(...)`](../tf/losses/get_regularization_losses.md): Gets the list of regularization losses.

[`get_total_loss(...)`](../tf/losses/get_total_loss.md): Returns a tensor whose value represents the total loss.

[`hinge_loss(...)`](../tf/losses/hinge_loss.md): Adds a hinge loss to the training procedure.

[`huber_loss(...)`](../tf/losses/huber_loss.md): Adds a Huber Loss term to the training procedure.

[`log_loss(...)`](../tf/losses/log_loss.md): Adds a Log Loss term to the training procedure.

[`mean_pairwise_squared_error(...)`](../tf/losses/mean_pairwise_squared_error.md): Adds a pairwise-errors-squared loss to the training procedure.

[`mean_squared_error(...)`](../tf/losses/mean_squared_error.md): Adds a Sum-of-Squares loss to the training procedure.

[`sigmoid_cross_entropy(...)`](../tf/losses/sigmoid_cross_entropy.md): Creates a cross-entropy loss using tf.nn.sigmoid_cross_entropy_with_logits.

[`softmax_cross_entropy(...)`](../tf/losses/softmax_cross_entropy.md): Creates a cross-entropy loss using tf.nn.softmax_cross_entropy_with_logits.

[`sparse_softmax_cross_entropy(...)`](../tf/losses/sparse_softmax_cross_entropy.md): Cross-entropy loss using `tf.nn.sparse_softmax_cross_entropy_with_logits`.

