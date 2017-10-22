<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.timeseries.NumpyReader" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="check_dataset_size"/>
<meta itemprop="property" content="read"/>
<meta itemprop="property" content="read_full"/>
</div>

# tf.contrib.timeseries.NumpyReader

## Class `NumpyReader`





Defined in [`tensorflow/contrib/timeseries/python/timeseries/input_pipeline.py`](https://www.tensorflow.org/code/tensorflow/contrib/timeseries/python/timeseries/input_pipeline.py).

A time series parser for feeding Numpy arrays to a `TimeSeriesInputFn`.

Avoids embedding data in the graph as constants.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    data,
    read_num_records_hint=4096
)
```

Numpy array input for a `TimeSeriesInputFn`.

#### Args:

* <b>`data`</b>: A dictionary mapping feature names to Numpy arrays, with two
    possible shapes (requires keys `TrainEvalFeatures.TIMES` and
    `TrainEvalFeatures.VALUES`):
      Univariate; `TIMES` and `VALUES` are both vectors of shape [series
        length]
      Multivariate; `TIMES` is a vector of shape [series length], `VALUES`
        has shape [series length x number of features].
    In any case, `VALUES` and any exogenous features must have their shapes
    prefixed by the shape of the value corresponding to the `TIMES` key.
* <b>`read_num_records_hint`</b>: The maximum number of samples to read at one time,
    for efficiency.

<h3 id="check_dataset_size"><code>check_dataset_size</code></h3>

``` python
check_dataset_size(minimum_dataset_size)
```

Raise an error if the dataset is too small.

<h3 id="read"><code>read</code></h3>

``` python
read()
```

Returns a large chunk of the Numpy arrays for later re-chunking.

<h3 id="read_full"><code>read_full</code></h3>

``` python
read_full()
```

Returns `Tensor` versions of the full Numpy arrays.



