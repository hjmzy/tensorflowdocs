<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.timeseries.CSVReader" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="check_dataset_size"/>
<meta itemprop="property" content="read"/>
<meta itemprop="property" content="read_full"/>
</div>

# tf.contrib.timeseries.CSVReader

## Class `CSVReader`





Defined in [`tensorflow/contrib/timeseries/python/timeseries/input_pipeline.py`](https://www.tensorflow.org/code/tensorflow/contrib/timeseries/python/timeseries/input_pipeline.py).

Reads from a collection of CSV-formatted files.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    filenames,
    column_names=(feature_keys.TrainEvalFeatures.TIMES, feature_keys.TrainEvalFeatures.VALUES),
    column_dtypes=None,
    skip_header_lines=None,
    read_num_records_hint=4096
)
```

CSV-parsing reader for a `TimeSeriesInputFn`.

#### Args:

* <b>`filenames`</b>: A filename or list of filenames to read the time series
      from. Each line must have columns corresponding to `column_names`.
* <b>`column_names`</b>: A list indicating names for each
      feature. `TrainEvalFeatures.TIMES` and `TrainEvalFeatures.VALUES` are
      required; `VALUES` may be repeated to indicate a multivariate series.
* <b>`column_dtypes`</b>: If provided, must be a list with the same length as
      `column_names`, indicating dtypes for each column. Defaults to
      `tf.int64` for `TrainEvalFeatures.TIMES` and `tf.float32` for
      everything else.
* <b>`skip_header_lines`</b>: Passed on to `tf.TextLineReader`; skips this number of
      lines at the beginning of each file.
* <b>`read_num_records_hint`</b>: When not reading a full dataset, indicates the
      number of records to parse/transfer in a single chunk (for
      efficiency). The actual number transferred at one time may be more or
      less.

#### Raises:

* <b>`ValueError`</b>: If required column names are not specified, or if lengths do
    not match.

<h3 id="check_dataset_size"><code>check_dataset_size</code></h3>

``` python
check_dataset_size(minimum_dataset_size)
```

When possible, raises an error if the dataset is too small.

This method allows TimeSeriesReaders to raise informative error messages if
the user has selected a window size in their TimeSeriesInputFn which is
larger than the dataset size. However, many TimeSeriesReaders will not have
access to a dataset size, in which case they do not need to override this
method.

#### Args:

* <b>`minimum_dataset_size`</b>: The minimum number of records which should be
    contained in the dataset. Readers should attempt to raise an error when
    possible if an epoch of data contains fewer records.

<h3 id="read"><code>read</code></h3>

``` python
read()
```

Reads a chunk of data from the `tf.ReaderBase` for later re-chunking.

<h3 id="read_full"><code>read_full</code></h3>

``` python
read_full()
```

Reads a full epoch of data into memory.



