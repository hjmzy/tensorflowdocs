<!-- DO NOT EDIT! Automatically generated file. -->
# Training (contrib)
[TOC]

Training and input utilities.

<h2 id="Splitting_sequence_inputs_into_minibatches_with_state_saving">Splitting sequence inputs into minibatches with state saving</h2>

Use [`tf.contrib.training.SequenceQueueingStateSaver`](../../api_docs/python/tf/contrib/training/SequenceQueueingStateSaver.md) or
its wrapper [`tf.contrib.training.batch_sequences_with_states`](../../api_docs/python/tf/contrib/training/batch_sequences_with_states.md) if
you have input data with a dynamic primary time / frame count axis which
you'd like to convert into fixed size segments during minibatching, and would
like to store state in the forward direction across segments of an example.

*   [`tf.contrib.training.batch_sequences_with_states`](../../api_docs/python/tf/contrib/training/batch_sequences_with_states.md)
*   [`tf.contrib.training.NextQueuedSequenceBatch`](../../api_docs/python/tf/contrib/training/NextQueuedSequenceBatch.md)
*   [`tf.contrib.training.SequenceQueueingStateSaver`](../../api_docs/python/tf/contrib/training/SequenceQueueingStateSaver.md)


<h2 id="Online_data_resampling">Online data resampling</h2>

To resample data with replacement on a per-example basis, use
[`tf.contrib.training.rejection_sample`](../../api_docs/python/tf/contrib/training/rejection_sample.md) or
[`tf.contrib.training.resample_at_rate`](../../api_docs/python/tf/contrib/training/resample_at_rate.md). For `rejection_sample`, provide
a boolean Tensor describing whether to accept or reject. Resulting batch sizes
are always the same. For `resample_at_rate`, provide the desired rate for each
example. Resulting batch sizes may vary. If you wish to specify relative
rates, rather than absolute ones, use [`tf.contrib.training.weighted_resample`](../../api_docs/python/tf/contrib/training/weighted_resample.md)
(which also returns the actual resampling rate used for each output example).

Use [`tf.contrib.training.stratified_sample`](../../api_docs/python/tf/contrib/training/stratified_sample.md) to resample without replacement
from the data to achieve a desired mix of class proportions that the Tensorflow
graph sees. For instance, if you have a binary classification dataset that is
99.9% class 1, a common approach is to resample from the data so that the data
is more balanced.

*   [`tf.contrib.training.rejection_sample`](../../api_docs/python/tf/contrib/training/rejection_sample.md)
*   [`tf.contrib.training.resample_at_rate`](../../api_docs/python/tf/contrib/training/resample_at_rate.md)
*   [`tf.contrib.training.stratified_sample`](../../api_docs/python/tf/contrib/training/stratified_sample.md)
*   [`tf.contrib.training.weighted_resample`](../../api_docs/python/tf/contrib/training/weighted_resample.md)

<h2 id="Bucketing">Bucketing</h2>

Use [`tf.contrib.training.bucket`](../../api_docs/python/tf/contrib/training/bucket.md) or
[`tf.contrib.training.bucket_by_sequence_length`](../../api_docs/python/tf/contrib/training/bucket_by_sequence_length.md) to stratify
minibatches into groups ("buckets").  Use `bucket_by_sequence_length`
with the argument `dynamic_pad=True` to receive minibatches of similarly
sized sequences for efficient training via `dynamic_rnn`.

*   [`tf.contrib.training.bucket`](../../api_docs/python/tf/contrib/training/bucket.md)
*   [`tf.contrib.training.bucket_by_sequence_length`](../../api_docs/python/tf/contrib/training/bucket_by_sequence_length.md)
