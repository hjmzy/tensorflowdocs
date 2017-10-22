<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.learn.extract_pandas_matrix" />
</div>

# tf.contrib.learn.extract_pandas_matrix

``` python
extract_pandas_matrix(data)
```



Defined in [`tensorflow/contrib/learn/python/learn/learn_io/pandas_io.py`](https://www.tensorflow.org/code/tensorflow/contrib/learn/python/learn/learn_io/pandas_io.py).

See the guide: [Learn (contrib) > Input processing](../../../../../api_guides/python/contrib.learn.md#Input_processing)

Extracts numpy matrix from pandas DataFrame.

#### Args:

* <b>`data`</b>: `pandas.DataFrame` containing the data to be extracted.


#### Returns:

A numpy `ndarray` of the DataFrame's values.