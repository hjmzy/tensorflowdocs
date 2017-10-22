<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.timeseries.WholeDatasetInputFn" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="create_batch"/>
</div>

# tf.contrib.timeseries.WholeDatasetInputFn

## Class `WholeDatasetInputFn`





Defined in [`tensorflow/contrib/timeseries/python/timeseries/input_pipeline.py`](https://www.tensorflow.org/code/tensorflow/contrib/timeseries/python/timeseries/input_pipeline.py).

Supports passing a full time series to a model for evaluation/inference.

Note that this `TimeSeriesInputFn` is not designed for high throughput, and
should not be used for training. It allows for sequential evaluation on a full
dataset (with sequential in-sample predictions), which then feeds naturally
into `predict_continuation_input_fn` for making out-of-sample
predictions. While this is useful for plotting and interactive use,
`RandomWindowInputFn` is better suited to training and quantitative
evaluation.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(time_series_reader)
```

Initialize the `TimeSeriesInputFn`.

#### Args:

* <b>`time_series_reader`</b>: A TimeSeriesReader object.

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__()
```



<h3 id="create_batch"><code>create_batch</code></h3>

``` python
create_batch()
```

A suitable `input_fn` for an `Estimator`'s `evaluate()`.

#### Returns:

A dictionary mapping feature names to `Tensors`, each shape
prefixed by [1, data set size] (i.e. a batch size of 1).



