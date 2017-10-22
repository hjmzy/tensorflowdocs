<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.seq2seq.LuongMonotonicAttention" />
<meta itemprop="property" content="alignments_size"/>
<meta itemprop="property" content="batch_size"/>
<meta itemprop="property" content="keys"/>
<meta itemprop="property" content="memory_layer"/>
<meta itemprop="property" content="query_layer"/>
<meta itemprop="property" content="values"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="initial_alignments"/>
</div>

# tf.contrib.seq2seq.LuongMonotonicAttention

## Class `LuongMonotonicAttention`





Defined in [`tensorflow/contrib/seq2seq/python/ops/attention_wrapper.py`](https://www.tensorflow.org/code/tensorflow/contrib/seq2seq/python/ops/attention_wrapper.py).

Monotonic attention mechanism with Luong-style energy function.

This type of attention encorces a monotonic constraint on the attention
distributions; that is once the model attends to a given point in the memory
it can't attend to any prior points at subsequence output timesteps.  It
achieves this by using the _monotonic_probability_fn instead of softmax to
construct its attention distributions.  Otherwise, it is equivalent to
LuongAttention.  This approach is proposed in

Colin Raffel, Minh-Thang Luong, Peter J. Liu, Ron J. Weiss, Douglas Eck,
"Online and Linear-Time Attention by Enforcing Monotonic Alignments."
ICML 2017.  https://arxiv.org/abs/1704.00784

## Properties

<h3 id="alignments_size"><code>alignments_size</code></h3>



<h3 id="batch_size"><code>batch_size</code></h3>



<h3 id="keys"><code>keys</code></h3>



<h3 id="memory_layer"><code>memory_layer</code></h3>



<h3 id="query_layer"><code>query_layer</code></h3>



<h3 id="values"><code>values</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    num_units,
    memory,
    memory_sequence_length=None,
    scale=False,
    score_mask_value=float('-inf'),
    sigmoid_noise=0.0,
    sigmoid_noise_seed=None,
    score_bias_init=0.0,
    mode='parallel',
    name='LuongMonotonicAttention'
)
```

Construct the Attention mechanism.

#### Args:

* <b>`num_units`</b>: The depth of the query mechanism.
* <b>`memory`</b>: The memory to query; usually the output of an RNN encoder.  This
    tensor should be shaped `[batch_size, max_time, ...]`.
  memory_sequence_length (optional): Sequence lengths for the batch entries
    in memory.  If provided, the memory tensor rows are masked with zeros
    for values past the respective sequence lengths.
* <b>`scale`</b>: Python boolean.  Whether to scale the energy term.
* <b>`score_mask_value`</b>: (optional): The mask value for score before passing into
    `probability_fn`. The default is -inf. Only used if
    `memory_sequence_length` is not None.
* <b>`sigmoid_noise`</b>: Standard deviation of pre-sigmoid noise.  See the docstring
    for `_monotonic_probability_fn` for more information.
* <b>`sigmoid_noise_seed`</b>: (optional) Random seed for pre-sigmoid noise.
* <b>`score_bias_init`</b>: Initial value for score bias scalar.  It's recommended to
    initialize this to a negative value when the length of the memory is
    large.
* <b>`mode`</b>: How to compute the attention distribution.  Must be one of
    'recursive', 'parallel', or 'hard'.  See the docstring for
    `tf.contrib.seq2seq.monotonic_attention` for more information.
* <b>`name`</b>: Name to use when creating ops.

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    query,
    previous_alignments
)
```

Score the query based on the keys and values.

#### Args:

* <b>`query`</b>: Tensor of dtype matching `self.values` and shape
    `[batch_size, query_depth]`.
* <b>`previous_alignments`</b>: Tensor of dtype matching `self.values` and shape
    `[batch_size, alignments_size]`
    (`alignments_size` is memory's `max_time`).


#### Returns:

* <b>`alignments`</b>: Tensor of dtype matching `self.values` and shape
    `[batch_size, alignments_size]` (`alignments_size` is memory's
    `max_time`).

<h3 id="initial_alignments"><code>initial_alignments</code></h3>

``` python
initial_alignments(
    batch_size,
    dtype
)
```

Creates the initial alignment values for the monotonic attentions.

Initializes to dirac distributions, i.e. [1, 0, 0, ...memory length..., 0]
for all entries in the batch.

#### Args:

* <b>`batch_size`</b>: `int32` scalar, the batch_size.
* <b>`dtype`</b>: The `dtype`.


#### Returns:

A `dtype` tensor shaped `[batch_size, alignments_size]`
(`alignments_size` is the values' `max_time`).



