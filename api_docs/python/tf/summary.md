<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary" />
</div>

# Module: tf.summary



Defined in [`tensorflow/python/summary/summary.py`](https://www.tensorflow.org/code/tensorflow/python/summary/summary.py).

Tensor summaries for exporting information about a model.

See the [Summary Operations](../../../api_guides/python/summary.md) guide.


## Classes

[`class Event`](../tf/Event.md)

[`class FileWriter`](../tf/summary/FileWriter.md): Writes `Summary` protocol buffers to event files.

[`class FileWriterCache`](../tf/summary/FileWriterCache.md): Cache for file writers.

[`class SessionLog`](../tf/SessionLog.md)

[`class Summary`](../tf/Summary.md)

[`class SummaryDescription`](../tf/summary/SummaryDescription.md)

[`class TaggedRunMetadata`](../tf/summary/TaggedRunMetadata.md)

## Functions

[`audio(...)`](../tf/summary/audio.md): Outputs a `Summary` protocol buffer with audio.

[`get_summary_description(...)`](../tf/summary/get_summary_description.md): Given a TensorSummary node_def, retrieve its SummaryDescription.

[`histogram(...)`](../tf/summary/histogram.md): Outputs a `Summary` protocol buffer with a histogram.

[`image(...)`](../tf/summary/image.md): Outputs a `Summary` protocol buffer with images.

[`merge(...)`](../tf/summary/merge.md): Merges summaries.

[`merge_all(...)`](../tf/summary/merge_all.md): Merges all summaries collected in the default graph.

[`scalar(...)`](../tf/summary/scalar.md): Outputs a `Summary` protocol buffer containing a single scalar value.

[`tensor_summary(...)`](../tf/summary/tensor_summary.md): Outputs a `Summary` protocol buffer with a serialized tensor.proto.

[`text(...)`](../tf/summary/text.md): Summarizes textual data.

