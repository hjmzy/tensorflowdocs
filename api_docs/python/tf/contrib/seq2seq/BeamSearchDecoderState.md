<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.seq2seq.BeamSearchDecoderState" />
<meta itemprop="property" content="cell_state"/>
<meta itemprop="property" content="finished"/>
<meta itemprop="property" content="lengths"/>
<meta itemprop="property" content="log_probs"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.contrib.seq2seq.BeamSearchDecoderState

## Class `BeamSearchDecoderState`





Defined in [`tensorflow/contrib/seq2seq/python/ops/beam_search_decoder.py`](https://www.tensorflow.org/code/tensorflow/contrib/seq2seq/python/ops/beam_search_decoder.py).



## Properties

<h3 id="cell_state"><code>cell_state</code></h3>

Alias for field number 0

<h3 id="finished"><code>finished</code></h3>

Alias for field number 2

<h3 id="lengths"><code>lengths</code></h3>

Alias for field number 3

<h3 id="log_probs"><code>log_probs</code></h3>

Alias for field number 1



## Methods

<h3 id="__new__"><code>__new__</code></h3>

``` python
__new__(
    _cls,
    cell_state,
    log_probs,
    finished,
    lengths
)
```

Create new instance of BeamSearchDecoderState(cell_state, log_probs, finished, lengths)



