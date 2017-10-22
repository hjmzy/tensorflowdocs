<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.timeseries.saved_model_utils.filter_continuation" />
</div>

# tf.contrib.timeseries.saved_model_utils.filter_continuation

``` python
filter_continuation(
    continue_from,
    signatures,
    session,
    features
)
```



Defined in [`tensorflow/contrib/timeseries/python/timeseries/saved_model_utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/timeseries/python/timeseries/saved_model_utils.py).

Perform filtering using an exported saved model.

Filtering refers to updating model state based on new observations.
Predictions based on the returned model state will be conditioned on these
observations.

#### Args:

* <b>`continue_from`</b>: A dictionary containing the results of either an Estimator's
    evaluate method or a previous filter_continuation. Used to determine the
    model state to start filtering from.
* <b>`signatures`</b>: The `MetaGraphDef` protocol buffer returned from
    `tf.saved_model.loader.load`. Used to determine the names of Tensors to
    feed and fetch. Must be from the same model as `continue_from`.
* <b>`session`</b>: The session to use. The session's graph must be the one into which
    `tf.saved_model.loader.load` loaded the model.
* <b>`features`</b>: A dictionary mapping keys to Numpy arrays, with several possible
    shapes (requires keys `FilteringFeatures.TIMES` and
    `FilteringFeatures.VALUES`):
      Single example; `TIMES` is a scalar and `VALUES` is either a scalar or a
        vector of length [number of features].
      Sequence; `TIMES` is a vector of shape [series length], `VALUES` either
        has shape [series length] (univariate) or [series length x number of
        features] (multivariate).
      Batch of sequences; `TIMES` is a vector of shape [batch size x series
        length], `VALUES` has shape [batch size x series length] or [batch
        size x series length x number of features].
    In any case, `VALUES` and any exogenous features must have their shapes
    prefixed by the shape of the value corresponding to the `TIMES` key.

#### Returns:

A dictionary containing model state updated to account for the observations
in `features`.