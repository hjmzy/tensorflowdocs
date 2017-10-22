<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.legacy_seq2seq.sequence_loss" />
</div>

# tf.contrib.legacy_seq2seq.sequence_loss

``` python
sequence_loss(
    logits,
    targets,
    weights,
    average_across_timesteps=True,
    average_across_batch=True,
    softmax_loss_function=None,
    name=None
)
```



Defined in [`tensorflow/contrib/legacy_seq2seq/python/ops/seq2seq.py`](https://www.tensorflow.org/code/tensorflow/contrib/legacy_seq2seq/python/ops/seq2seq.py).

Weighted cross-entropy loss for a sequence of logits, batch-collapsed.

#### Args:

* <b>`logits`</b>: List of 2D Tensors of shape [batch_size x num_decoder_symbols].
* <b>`targets`</b>: List of 1D batch-sized int32 Tensors of the same length as logits.
* <b>`weights`</b>: List of 1D batch-sized float-Tensors of the same length as logits.
* <b>`average_across_timesteps`</b>: If set, divide the returned cost by the total
    label weight.
* <b>`average_across_batch`</b>: If set, divide the returned cost by the batch size.
* <b>`softmax_loss_function`</b>: Function (labels, logits) -> loss-batch
    to be used instead of the standard softmax (the default if this is None).
    **Note that to avoid confusion, it is required for the function to accept
    named arguments.**
* <b>`name`</b>: Optional name for this operation, defaults to "sequence_loss".


#### Returns:

A scalar float Tensor: The average log-perplexity per symbol (weighted).


#### Raises:

* <b>`ValueError`</b>: If len(logits) is different from len(targets) or len(weights).