<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data" />
</div>

# Module: tf.contrib.data



Defined in [`tensorflow/contrib/data/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/__init__.py).

`tf.contrib.data.Dataset` API for input pipelines.

See the [Importing Data](../../../../programmers_guide/datasets.md) Programmer's Guide for an overview.




## Classes

[`class Dataset`](../../tf/contrib/data/Dataset.md): Represents a potentially large set of elements.

[`class FixedLengthRecordDataset`](../../tf/contrib/data/FixedLengthRecordDataset.md): A `Dataset` of fixed-length records from one or more binary files.

[`class Iterator`](../../tf/data/Iterator.md): Represents the state of iterating through a `Dataset`.

[`class TFRecordDataset`](../../tf/contrib/data/TFRecordDataset.md): A `Dataset` comprising records from one or more TFRecord files.

[`class TextLineDataset`](../../tf/contrib/data/TextLineDataset.md): A `Dataset` comprising lines from one or more text files.

## Functions

[`batch_and_drop_remainder(...)`](../../tf/contrib/data/batch_and_drop_remainder.md): A batching transformation that omits the final small batch (if present).

[`dense_to_sparse_batch(...)`](../../tf/contrib/data/dense_to_sparse_batch.md): A transformation that batches ragged elements into `tf.SparseTensor`s.

[`enumerate_dataset(...)`](../../tf/contrib/data/enumerate_dataset.md): A transformation that enumerate the elements of a dataset.

[`get_single_element(...)`](../../tf/contrib/data/get_single_element.md): Returns the single element in `dataset` as a nested structure of tensors.

[`group_by_window(...)`](../../tf/contrib/data/group_by_window.md): A transformation that groups windows of elements by key and reduces them.

[`ignore_errors(...)`](../../tf/contrib/data/ignore_errors.md): Creates a `Dataset` from another `Dataset` and silently ignores any errors.

[`read_batch_features(...)`](../../tf/contrib/data/read_batch_features.md): Reads batches of Examples.

[`rejection_resample(...)`](../../tf/contrib/data/rejection_resample.md): A transformation that resamples a dataset to achieve a target distribution.

[`sloppy_interleave(...)`](../../tf/contrib/data/sloppy_interleave.md): A non-deterministic version of the `Dataset.interleave()` transformation.

[`unbatch(...)`](../../tf/contrib/data/unbatch.md): A Transformation which splits the elements of a dataset.

