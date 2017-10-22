<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.cudnn_rnn.CudnnGRU" />
<meta itemprop="property" content="direction"/>
<meta itemprop="property" content="input_mode"/>
<meta itemprop="property" content="input_size"/>
<meta itemprop="property" content="num_layers"/>
<meta itemprop="property" content="num_units"/>
<meta itemprop="property" content="rnn_mode"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="canonical_to_params"/>
<meta itemprop="property" content="params_size"/>
<meta itemprop="property" content="params_to_canonical"/>
</div>

# tf.contrib.cudnn_rnn.CudnnGRU

## Class `CudnnGRU`





Defined in [`tensorflow/contrib/cudnn_rnn/python/ops/cudnn_rnn_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/cudnn_rnn/python/ops/cudnn_rnn_ops.py).

Cudnn implementation of the GRU model.
Cudnn RNN has an opaque parameter buffer that can be used for inference and
training. But it is possible that the layout of the parameter buffers
changes between generations. So it is highly recommended to use
CudnnOpaqueParamsSaveable to save and restore weights and biases in a
canonical format.

This is a typical use case:

  * The user creates a CudnnRNN model.
  * The user query that parameter buffer size.
  * The user creates a variable of that size that serves as the parameter
      buffers.
  * The user either initialize the parameter buffer, or load the canonical
      weights into the parameter buffer.
  * The user calls the model with the parameter buffer for inference, or
      training.
  * If training, the user creates a Saver object.
  * If training, the user creates a CudnnOpaqueParamsSaveable object from the
      parameter buffer for it to be later saved in the canonical format. When
      creating a CudnnOpaqueParamsSaveable object, a name could be provided,
      which is useful in distinguishing the names of multiple
      CudnnOpaqueParamsSaveable objects (e.g. for an encoder-decoder model).
  * Once a while, the user saves the parameter buffer into model checkpoints
      with Saver.save().
  * When restoring, the user creates a CudnnOpaqueParamsSaveable object and
    uses Saver.restore() to restore the parameter buffer from the canonical
    format to a user-defined format, as well as to restore other savable
    objects in the checkpoint file.

## Properties

<h3 id="direction"><code>direction</code></h3>



<h3 id="input_mode"><code>input_mode</code></h3>



<h3 id="input_size"><code>input_size</code></h3>



<h3 id="num_layers"><code>num_layers</code></h3>



<h3 id="num_units"><code>num_units</code></h3>



<h3 id="rnn_mode"><code>rnn_mode</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    num_layers,
    num_units,
    input_size,
    input_mode=CUDNN_INPUT_LINEAR_MODE,
    direction=CUDNN_RNN_UNIDIRECTION,
    dtype=tf.float32,
    dropout=0.0,
    seed=0
)
```

Creates a Cudnn RNN model from model without hidden-state C.

#### Args:

* <b>`num_layers`</b>: the number of layers for the RNN model.
* <b>`num_units`</b>: the number of units within the RNN model.
* <b>`input_size`</b>: the size of the input, it could be different from the
      num_units.
* <b>`input_mode`</b>: indicate whether there is a linear projection between the
      input and The actual computation before the first layer. It could be
      'skip_input', 'linear_input' or 'auto_select'.
      'skip_input' is only allowed when input_size == num_units;
      'auto_select' implies 'skip_input' when input_size == num_units;
      otherwise, it implies 'linear_input'.
* <b>`direction`</b>: the direction model that the model operates. Could be either
      'unidirectional' or 'bidirectional'
* <b>`dtype`</b>: dtype of params, tf.float32 or tf.float64.
* <b>`dropout`</b>: whether to enable dropout. With it is 0, dropout is disabled.
* <b>`seed`</b>: the seed used for initializing dropout.


#### Raises:

* <b>`ValueError`</b>: if direction is not 'unidirectional' or 'bidirectional'.

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    input_data,
    input_h,
    params,
    is_training=True
)
```

Runs the forward step for the Cudnn LSTM model.

#### Args:

* <b>`input_data`</b>: the input sequence to the RNN model. A Tensor of shape [?,
    batch_size, input_size].
* <b>`input_h`</b>: the initial hidden state for h. A Tensor of shape [num_layers,
    batch_size, num_units].
* <b>`params`</b>: the parameter buffer created for this model.
* <b>`is_training`</b>: whether this operation will be used in training or inference.

#### Returns:

* <b>`output`</b>: the output sequuence.
* <b>`output_h`</b>: the final state for h.

<h3 id="canonical_to_params"><code>canonical_to_params</code></h3>

``` python
canonical_to_params(
    weights,
    biases
)
```

Converts params from the canonical format to a specific format of cuDNN.

#### Args:

* <b>`weights`</b>: a Tensor for weight parameters.
* <b>`biases`</b>: a Tensor for bias parameters.


#### Returns:

A function for the canonical-to-params-to-specific conversion..

<h3 id="params_size"><code>params_size</code></h3>

``` python
params_size()
```

Calculates the size of the opaque parameter buffer needed for this model.

#### Returns:

The calculated parameter buffer size.

<h3 id="params_to_canonical"><code>params_to_canonical</code></h3>

``` python
params_to_canonical(params)
```

Converts params from a specific format of cuDNN to the canonical format.

#### Args:

* <b>`params`</b>: a Variable for weight and bias parameters.


#### Returns:

A function for the specific-to-canonical conversion.



