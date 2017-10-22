<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.losses.softmax_cross_entropy" />
</div>

# tf.contrib.losses.softmax_cross_entropy

``` python
softmax_cross_entropy(
    logits,
    onehot_labels,
    weights=1.0,
    label_smoothing=0,
    scope=None
)
```



Defined in [`tensorflow/contrib/losses/python/losses/loss_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/losses/python/losses/loss_ops.py).

See the guide: [Losses (contrib) > Loss operations for use in neural networks.](../../../../../api_guides/python/contrib.losses.md#Loss_operations_for_use_in_neural_networks_)

Creates a cross-entropy loss using tf.nn.softmax_cross_entropy_with_logits. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2016-12-30.
Instructions for updating:
Use tf.losses.softmax_cross_entropy instead. Note that the order of the logits and labels arguments has been changed.

`weights` acts as a coefficient for the loss. If a scalar is provided,
then the loss is simply scaled by the given value. If `weights` is a
tensor of size [`batch_size`], then the loss weights apply to each
corresponding sample.

If `label_smoothing` is nonzero, smooth the labels towards 1/num_classes:
    new_onehot_labels = onehot_labels * (1 - label_smoothing)
                        + label_smoothing / num_classes

#### Args:

* <b>`logits`</b>: [batch_size, num_classes] logits outputs of the network .
* <b>`onehot_labels`</b>: [batch_size, num_classes] one-hot-encoded labels.
* <b>`weights`</b>: Coefficients for the loss. The tensor must be a scalar or a tensor
    of shape [batch_size].
* <b>`label_smoothing`</b>: If greater than 0 then smooth the labels.
* <b>`scope`</b>: the scope for the operations performed in computing the loss.


#### Returns:

A scalar `Tensor` representing the mean loss value.


#### Raises:

* <b>`ValueError`</b>: If the shape of `logits` doesn't match that of `onehot_labels`
    or if the shape of `weights` is invalid or if `weights` is None.