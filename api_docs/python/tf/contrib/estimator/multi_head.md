<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.estimator.multi_head" />
</div>

# tf.contrib.estimator.multi_head

``` python
multi_head(
    heads,
    head_weights=None
)
```



Defined in [`tensorflow/contrib/estimator/python/estimator/multi_head.py`](https://www.tensorflow.org/code/tensorflow/contrib/estimator/python/estimator/multi_head.py).

Creates a `_Head` for multi-objective learning.

This class merges the output of multiple `_Head` objects.
Specifically:
* For training, sums losses of each head, calls `train_op_fn` with this
  final loss.
* For eval, merges metrics by adding `head.name` suffix to the keys in eval
  metrics, such as `precision/head1`, `precision/head2`.
* For prediction, merges predictions and updates keys in prediction dict to a
  2-tuple, `(head.name, prediction_key)`. Merges `export_outputs` such that
  by default the first head is served.

Usage:

```python
# In `input_fn` specify labels as a dict keyed by head name:
def input_fn():
  features = ...
  labels1 = ...
  labels2 = ...
  return features, {'head1': labels1, 'head2': labels2}

# In `model_fn`, specify logits as a dict keyed by head name:
def model_fn(features, labels, mode):
  # Create simple heads and specify head name.
  head1 = multi_class_head(n_classes=3, name='head1')
  head2 = binary_classification_head(name='head2')
  # Create multi-head from two simple heads.
  head = multi_head([head1, head2])
  # Create logits for each head, and combine them into a dict.
  logits1, logits2 = logit_fn()
  logits = {'head1': logits1, 'head2': logits2}
  # Return the merged EstimatorSpec
  return head.create_estimator_spec(..., logits=logits, ...)

# Create an estimator with this model_fn.
estimator = tf.estimator.Estimator(model_fn=model_fn)
estimator.train(input_fn=input_fn, steps=100)
```

#### Args:

* <b>`heads`</b>: List or tuple of `_Head` instances. All heads must have `name`
    specified. The first head in the list is the default used at serving time.
* <b>`head_weights`</b>: Optional list of weights, same length as `heads`. Used when
    merging losses to calculate the weighted sum of losses from each head. If
    `None`, all losses are weighted equally.


#### Returns:

A instance of `_Head` that merges multiple heads.


#### Raises:

* <b>`ValueError`</b>: If `heads` is empty.
* <b>`ValueError`</b>: If any of the `heads` does not have `name` specified.
* <b>`ValueError`</b>: If `heads` and `head_weights` have different size.