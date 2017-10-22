<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.cosine_distance" />
</div>

# tf.losses.cosine_distance

``` python
cosine_distance(
    labels,
    predictions,
    axis=None,
    weights=1.0,
    scope=None,
    loss_collection=tf.GraphKeys.LOSSES,
    reduction=Reduction.SUM_BY_NONZERO_WEIGHTS,
    dim=None
)
```



Defined in [`tensorflow/python/ops/losses/losses_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/losses/losses_impl.py).

Adds a cosine-distance loss to the training procedure. (deprecated arguments)

SOME ARGUMENTS ARE DEPRECATED. They will be removed in a future version.
Instructions for updating:
dim is deprecated, use axis instead

Note that the function assumes that `predictions` and `labels` are already
unit-normalized.

#### Args:

* <b>`labels`</b>: `Tensor` whose shape matches 'predictions'
* <b>`predictions`</b>: An arbitrary matrix.
* <b>`axis`</b>: The dimension along which the cosine distance is computed.
* <b>`weights`</b>: Optional `Tensor` whose rank is either 0, or the same rank as
    `labels`, and must be broadcastable to `labels` (i.e., all dimensions must
    be either `1`, or the same as the corresponding `losses` dimension).
* <b>`scope`</b>: The scope for the operations performed in computing the loss.
* <b>`loss_collection`</b>: collection to which this loss will be added.
* <b>`reduction`</b>: Type of reduction to apply to loss.
* <b>`dim`</b>: The old (deprecated) name for `axis`.


#### Returns:

Weighted loss float `Tensor`. If `reduction` is `NONE`, this has the same
shape as `labels`; otherwise, it is scalar.


#### Raises:

* <b>`ValueError`</b>: If `predictions` shape doesn't match `labels` shape, or
    `axis`, `labels`, `predictions` or `weights` is `None`.