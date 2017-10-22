<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.scattered_embedding_column" />
</div>

# tf.contrib.layers.scattered_embedding_column

``` python
scattered_embedding_column(
    column_name,
    size,
    dimension,
    hash_key,
    combiner='mean',
    initializer=None
)
```



Defined in [`tensorflow/contrib/layers/python/layers/feature_column.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/feature_column.py).

See the guide: [Layers (contrib) > Feature columns](../../../../../api_guides/python/contrib.layers.md#Feature_columns)

Creates an embedding column of a sparse feature using parameter hashing.

This is a useful shorthand when you have a sparse feature you want to use an
embedding for, but also want to hash the embedding's values in each dimension
to a variable based on a different hash.

Specifically, the i-th embedding component of a value v is found by retrieving
an embedding weight whose index is a fingerprint of the pair (v,i).

An embedding column with sparse_column_with_hash_bucket such as

    embedding_column(
      sparse_column_with_hash_bucket(column_name, bucket_size),
      dimension)

could be replaced by

    scattered_embedding_column(
      column_name,
      size=bucket_size * dimension,
      dimension=dimension,
      hash_key=tf.contrib.layers.SPARSE_FEATURE_CROSS_DEFAULT_HASH_KEY)

for the same number of embedding parameters. This should hopefully reduce the
impact of collisions, but adds the cost of slowing down training.

#### Args:

* <b>`column_name`</b>: A string defining sparse column name.
* <b>`size`</b>: An integer specifying the number of parameters in the embedding layer.
* <b>`dimension`</b>: An integer specifying dimension of the embedding.
* <b>`hash_key`</b>: Specify the hash_key that will be used by the `FingerprintCat64`
    function to combine the crosses fingerprints on SparseFeatureCrossOp.
* <b>`combiner`</b>: A string specifying how to reduce if there are multiple entries
    in a single row. Currently "mean", "sqrtn" and "sum" are supported, with
    "mean" the default. "sqrtn" often achieves good accuracy, in particular
    with bag-of-words columns. Each of this can be thought as example level
    normalizations on the column:
      * "sum": do not normalize features in the column
      * "mean": do l1 normalization on features in the column
      * "sqrtn": do l2 normalization on features in the column
    For more information: `tf.embedding_lookup_sparse`.
* <b>`initializer`</b>: A variable initializer function to be used in embedding
    variable initialization. If not specified, defaults to
    `tf.truncated_normal_initializer` with mean 0 and standard deviation 0.1.


#### Returns:

A _ScatteredEmbeddingColumn.


#### Raises:

* <b>`ValueError`</b>: if dimension or size is not a positive integer; or if combiner
    is not supported.