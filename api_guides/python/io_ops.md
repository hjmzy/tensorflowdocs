<!-- DO NOT EDIT! Automatically generated file. -->
# Inputs and Readers

Note: Functions taking `Tensor` arguments can also take anything accepted by
[`tf.convert_to_tensor`](../../api_docs/python/tf/convert_to_tensor.md).

[TOC]

<h2 id="Placeholders">Placeholders</h2>

TensorFlow provides a placeholder operation that must be fed with data
on execution.  For more info, see the section on [Feeding data](../../api_guides/python/reading_data.md#feeding).

*   [`tf.placeholder`](../../api_docs/python/tf/placeholder.md)
*   [`tf.placeholder_with_default`](../../api_docs/python/tf/placeholder_with_default.md)

For feeding `SparseTensor`s which are composite type,
there is a convenience function:

*   [`tf.sparse_placeholder`](../../api_docs/python/tf/sparse_placeholder.md)

<h2 id="Readers">Readers</h2>

TensorFlow provides a set of Reader classes for reading data formats.
For more information on inputs and readers, see [Reading data](../../api_guides/python/reading_data.md).

*   [`tf.ReaderBase`](../../api_docs/python/tf/ReaderBase.md)
*   [`tf.TextLineReader`](../../api_docs/python/tf/TextLineReader.md)
*   [`tf.WholeFileReader`](../../api_docs/python/tf/WholeFileReader.md)
*   [`tf.IdentityReader`](../../api_docs/python/tf/IdentityReader.md)
*   [`tf.TFRecordReader`](../../api_docs/python/tf/TFRecordReader.md)
*   [`tf.FixedLengthRecordReader`](../../api_docs/python/tf/FixedLengthRecordReader.md)

<h2 id="Converting">Converting</h2>

TensorFlow provides several operations that you can use to convert various data
formats into tensors.

*   [`tf.decode_csv`](../../api_docs/python/tf/decode_csv.md)
*   [`tf.decode_raw`](../../api_docs/python/tf/decode_raw.md)

- - -

### Example protocol buffer

TensorFlow's [recommended format for training examples](../../api_guides/python/reading_data.md#standard-tensorflow-format)
is serialized `Example` protocol buffers, [described
here](https://www.tensorflow.org/code/tensorflow/core/example/example.proto).
They contain `Features`, [described
here](https://www.tensorflow.org/code/tensorflow/core/example/feature.proto).

*   [`tf.VarLenFeature`](../../api_docs/python/tf/VarLenFeature.md)
*   [`tf.FixedLenFeature`](../../api_docs/python/tf/FixedLenFeature.md)
*   [`tf.FixedLenSequenceFeature`](../../api_docs/python/tf/FixedLenSequenceFeature.md)
*   [`tf.SparseFeature`](../../api_docs/python/tf/SparseFeature.md)
*   [`tf.parse_example`](../../api_docs/python/tf/parse_example.md)
*   [`tf.parse_single_example`](../../api_docs/python/tf/parse_single_example.md)
*   [`tf.parse_tensor`](../../api_docs/python/tf/parse_tensor.md)
*   [`tf.decode_json_example`](../../api_docs/python/tf/decode_json_example.md)

<h2 id="Queues">Queues</h2>

TensorFlow provides several implementations of 'Queues', which are
structures within the TensorFlow computation graph to stage pipelines
of tensors together. The following describe the basic Queue interface
and some implementations.  To see an example use, see [Threading and Queues](../../api_guides/python/threading_and_queues.md).

*   [`tf.QueueBase`](../../api_docs/python/tf/QueueBase.md)
*   [`tf.FIFOQueue`](../../api_docs/python/tf/FIFOQueue.md)
*   [`tf.PaddingFIFOQueue`](../../api_docs/python/tf/PaddingFIFOQueue.md)
*   [`tf.RandomShuffleQueue`](../../api_docs/python/tf/RandomShuffleQueue.md)
*   [`tf.PriorityQueue`](../../api_docs/python/tf/PriorityQueue.md)

<h2 id="Conditional_Accumulators">Conditional Accumulators</h2>

*   [`tf.ConditionalAccumulatorBase`](../../api_docs/python/tf/ConditionalAccumulatorBase.md)
*   [`tf.ConditionalAccumulator`](../../api_docs/python/tf/ConditionalAccumulator.md)
*   [`tf.SparseConditionalAccumulator`](../../api_docs/python/tf/SparseConditionalAccumulator.md)

<h2 id="Dealing_with_the_filesystem">Dealing with the filesystem</h2>

*   [`tf.matching_files`](../../api_docs/python/tf/matching_files.md)
*   [`tf.read_file`](../../api_docs/python/tf/read_file.md)
*   [`tf.write_file`](../../api_docs/python/tf/write_file.md)

<h2 id="Input_pipeline">Input pipeline</h2>

TensorFlow functions for setting up an input-prefetching pipeline.
Please see the [reading data how-to](../../api_guides/python/reading_data.md)
for context.

### Beginning of an input pipeline

The "producer" functions add a queue to the graph and a corresponding
`QueueRunner` for running the subgraph that fills that queue.

*   [`tf.train.match_filenames_once`](../../api_docs/python/tf/train/match_filenames_once.md)
*   [`tf.train.limit_epochs`](../../api_docs/python/tf/train/limit_epochs.md)
*   [`tf.train.input_producer`](../../api_docs/python/tf/train/input_producer.md)
*   [`tf.train.range_input_producer`](../../api_docs/python/tf/train/range_input_producer.md)
*   [`tf.train.slice_input_producer`](../../api_docs/python/tf/train/slice_input_producer.md)
*   [`tf.train.string_input_producer`](../../api_docs/python/tf/train/string_input_producer.md)

### Batching at the end of an input pipeline

These functions add a queue to the graph to assemble a batch of
examples, with possible shuffling.  They also add a `QueueRunner` for
running the subgraph that fills that queue.

Use [`tf.train.batch`](../../api_docs/python/tf/train/batch.md) or [`tf.train.batch_join`](../../api_docs/python/tf/train/batch_join.md) for batching
examples that have already been well shuffled.  Use
[`tf.train.shuffle_batch`](../../api_docs/python/tf/train/shuffle_batch.md) or
[`tf.train.shuffle_batch_join`](../../api_docs/python/tf/train/shuffle_batch_join.md) for examples that would
benefit from additional shuffling.

Use [`tf.train.batch`](../../api_docs/python/tf/train/batch.md) or [`tf.train.shuffle_batch`](../../api_docs/python/tf/train/shuffle_batch.md) if you want a
single thread producing examples to batch, or if you have a
single subgraph producing examples but you want to run it in *N* threads
(where you increase *N* until it can keep the queue full).  Use
[`tf.train.batch_join`](../../api_docs/python/tf/train/batch_join.md) or [`tf.train.shuffle_batch_join`](../../api_docs/python/tf/train/shuffle_batch_join.md)
if you have *N* different subgraphs producing examples to batch and you
want them run by *N* threads. Use `maybe_*` to enqueue conditionally.

*   [`tf.train.batch`](../../api_docs/python/tf/train/batch.md)
*   [`tf.train.maybe_batch`](../../api_docs/python/tf/train/maybe_batch.md)
*   [`tf.train.batch_join`](../../api_docs/python/tf/train/batch_join.md)
*   [`tf.train.maybe_batch_join`](../../api_docs/python/tf/train/maybe_batch_join.md)
*   [`tf.train.shuffle_batch`](../../api_docs/python/tf/train/shuffle_batch.md)
*   [`tf.train.maybe_shuffle_batch`](../../api_docs/python/tf/train/maybe_shuffle_batch.md)
*   [`tf.train.shuffle_batch_join`](../../api_docs/python/tf/train/shuffle_batch_join.md)
*   [`tf.train.maybe_shuffle_batch_join`](../../api_docs/python/tf/train/maybe_shuffle_batch_join.md)
