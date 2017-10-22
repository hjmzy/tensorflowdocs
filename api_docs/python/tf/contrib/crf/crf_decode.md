<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.crf.crf_decode" />
</div>

# tf.contrib.crf.crf_decode

``` python
crf_decode(
    potentials,
    transition_params,
    sequence_length
)
```



Defined in [`tensorflow/contrib/crf/python/ops/crf.py`](https://www.tensorflow.org/code/tensorflow/contrib/crf/python/ops/crf.py).

Decode the highest scoring sequence of tags in TensorFlow.

This is a function for tensor.

#### Args:

* <b>`potentials`</b>: A [batch_size, max_seq_len, num_tags] tensor, matrix of
            unary potentials.
* <b>`transition_params`</b>: A [num_tags, num_tags] tensor, matrix of
            binary potentials.
* <b>`sequence_length`</b>: A [batch_size] tensor, containing sequence lengths.


#### Returns:

* <b>`decode_tags`</b>: A [batch_size, max_seq_len] tensor, with dtype tf.int32.
              Contains the highest scoring tag indicies.
* <b>`best_score`</b>: A [batch_size] tensor, containing the score of decode_tags.