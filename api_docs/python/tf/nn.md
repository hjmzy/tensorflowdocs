<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn" />
<meta itemprop="property" content="swish"/>
</div>

# Module: tf.nn



Defined in [`tensorflow/python/ops/nn.py`](https://www.tensorflow.org/code/tensorflow/python/ops/nn.py).

Neural network support.

See the [Neural Network](../../../api_guides/python/nn.md) guide.


## Modules

[`rnn_cell`](../tf/nn/rnn_cell.md) module: Module for constructing RNN Cells.

## Functions

[`all_candidate_sampler(...)`](../tf/nn/all_candidate_sampler.md): Generate the set of all classes.

[`atrous_conv2d(...)`](../tf/nn/atrous_conv2d.md): Atrous convolution (a.k.a. convolution with holes or dilated convolution).

[`atrous_conv2d_transpose(...)`](../tf/nn/atrous_conv2d_transpose.md): The transpose of `atrous_conv2d`.

[`avg_pool(...)`](../tf/nn/avg_pool.md): Performs the average pooling on the input.

[`avg_pool3d(...)`](../tf/nn/avg_pool3d.md): Performs 3D average pooling on the input.

[`batch_norm_with_global_normalization(...)`](../tf/nn/batch_norm_with_global_normalization.md): Batch normalization.

[`batch_normalization(...)`](../tf/nn/batch_normalization.md): Batch normalization.

[`bias_add(...)`](../tf/nn/bias_add.md): Adds `bias` to `value`.

[`bidirectional_dynamic_rnn(...)`](../tf/nn/bidirectional_dynamic_rnn.md): Creates a dynamic version of bidirectional recurrent neural network.

[`compute_accidental_hits(...)`](../tf/nn/compute_accidental_hits.md): Compute the position ids in `sampled_candidates` matching `true_classes`.

[`conv1d(...)`](../tf/nn/conv1d.md): Computes a 1-D convolution given 3-D input and filter tensors.

[`conv2d(...)`](../tf/nn/conv2d.md): Computes a 2-D convolution given 4-D `input` and `filter` tensors.

[`conv2d_backprop_filter(...)`](../tf/nn/conv2d_backprop_filter.md): Computes the gradients of convolution with respect to the filter.

[`conv2d_backprop_input(...)`](../tf/nn/conv2d_backprop_input.md): Computes the gradients of convolution with respect to the input.

[`conv2d_transpose(...)`](../tf/nn/conv2d_transpose.md): The transpose of `conv2d`.

[`conv3d(...)`](../tf/nn/conv3d.md): Computes a 3-D convolution given 5-D `input` and `filter` tensors.

[`conv3d_backprop_filter_v2(...)`](../tf/nn/conv3d_backprop_filter_v2.md): Computes the gradients of 3-D convolution with respect to the filter.

[`conv3d_transpose(...)`](../tf/nn/conv3d_transpose.md): The transpose of `conv3d`.

[`convolution(...)`](../tf/nn/convolution.md): Computes sums of N-D convolutions (actually cross-correlation).

[`crelu(...)`](../tf/nn/crelu.md): Computes Concatenated ReLU.

[`ctc_beam_search_decoder(...)`](../tf/nn/ctc_beam_search_decoder.md): Performs beam search decoding on the logits given in input.

[`ctc_greedy_decoder(...)`](../tf/nn/ctc_greedy_decoder.md): Performs greedy decoding on the logits given in input (best path).

[`ctc_loss(...)`](../tf/nn/ctc_loss.md): Computes the CTC (Connectionist Temporal Classification) Loss.

[`depthwise_conv2d(...)`](../tf/nn/depthwise_conv2d.md): Depthwise 2-D convolution.

[`depthwise_conv2d_native(...)`](../tf/nn/depthwise_conv2d_native.md): Computes a 2-D depthwise convolution given 4-D `input` and `filter` tensors.

[`depthwise_conv2d_native_backprop_filter(...)`](../tf/nn/depthwise_conv2d_native_backprop_filter.md): Computes the gradients of depthwise convolution with respect to the filter.

[`depthwise_conv2d_native_backprop_input(...)`](../tf/nn/depthwise_conv2d_native_backprop_input.md): Computes the gradients of depthwise convolution with respect to the input.

[`dilation2d(...)`](../tf/nn/dilation2d.md): Computes the grayscale dilation of 4-D `input` and 3-D `filter` tensors.

[`dropout(...)`](../tf/nn/dropout.md): Computes dropout.

[`dynamic_rnn(...)`](../tf/nn/dynamic_rnn.md): Creates a recurrent neural network specified by RNNCell `cell`.

[`elu(...)`](../tf/nn/elu.md): Computes exponential linear: `exp(features) - 1` if < 0, `features` otherwise.

[`embedding_lookup(...)`](../tf/nn/embedding_lookup.md): Looks up `ids` in a list of embedding tensors.

[`embedding_lookup_sparse(...)`](../tf/nn/embedding_lookup_sparse.md): Computes embeddings for the given ids and weights.

[`erosion2d(...)`](../tf/nn/erosion2d.md): Computes the grayscale erosion of 4-D `value` and 3-D `kernel` tensors.

[`fixed_unigram_candidate_sampler(...)`](../tf/nn/fixed_unigram_candidate_sampler.md): Samples a set of classes using the provided (fixed) base distribution.

[`fractional_avg_pool(...)`](../tf/nn/fractional_avg_pool.md): Performs fractional average pooling on the input.

[`fractional_max_pool(...)`](../tf/nn/fractional_max_pool.md): Performs fractional max pooling on the input.

[`fused_batch_norm(...)`](../tf/nn/fused_batch_norm.md): Batch normalization.

[`in_top_k(...)`](../tf/nn/in_top_k.md): Says whether the targets are in the top `K` predictions.

[`l2_loss(...)`](../tf/nn/l2_loss.md): L2 Loss.

[`l2_normalize(...)`](../tf/nn/l2_normalize.md): Normalizes along dimension `dim` using an L2 norm.

[`leaky_relu(...)`](../tf/nn/leaky_relu.md): Compute the Leaky ReLU activation function.

[`learned_unigram_candidate_sampler(...)`](../tf/nn/learned_unigram_candidate_sampler.md): Samples a set of classes from a distribution learned during training.

[`local_response_normalization(...)`](../tf/nn/local_response_normalization.md): Local Response Normalization.

[`log_poisson_loss(...)`](../tf/nn/log_poisson_loss.md): Computes log Poisson loss given `log_input`.

[`log_softmax(...)`](../tf/nn/log_softmax.md): Computes log softmax activations.

[`log_uniform_candidate_sampler(...)`](../tf/nn/log_uniform_candidate_sampler.md): Samples a set of classes using a log-uniform (Zipfian) base distribution.

[`lrn(...)`](../tf/nn/local_response_normalization.md): Local Response Normalization.

[`max_pool(...)`](../tf/nn/max_pool.md): Performs the max pooling on the input.

[`max_pool3d(...)`](../tf/nn/max_pool3d.md): Performs 3D max pooling on the input.

[`max_pool_with_argmax(...)`](../tf/nn/max_pool_with_argmax.md): Performs max pooling on the input and outputs both max values and indices.

[`moments(...)`](../tf/nn/moments.md): Calculate the mean and variance of `x`.

[`nce_loss(...)`](../tf/nn/nce_loss.md): Computes and returns the noise-contrastive estimation training loss.

[`normalize_moments(...)`](../tf/nn/normalize_moments.md): Calculate the mean and variance of based on the sufficient statistics.

[`pool(...)`](../tf/nn/pool.md): Performs an N-D pooling operation.

[`quantized_avg_pool(...)`](../tf/nn/quantized_avg_pool.md): Produces the average pool of the input tensor for quantized types.

[`quantized_conv2d(...)`](../tf/nn/quantized_conv2d.md): Computes a 2D convolution given quantized 4D input and filter tensors.

[`quantized_max_pool(...)`](../tf/nn/quantized_max_pool.md): Produces the max pool of the input tensor for quantized types.

[`quantized_relu_x(...)`](../tf/nn/quantized_relu_x.md): Computes Quantized Rectified Linear X: `min(max(features, 0), max_value)`

[`raw_rnn(...)`](../tf/nn/raw_rnn.md): Creates an `RNN` specified by RNNCell `cell` and loop function `loop_fn`.

[`relu(...)`](../tf/nn/relu.md): Computes rectified linear: `max(features, 0)`.

[`relu6(...)`](../tf/nn/relu6.md): Computes Rectified Linear 6: `min(max(features, 0), 6)`.

[`relu_layer(...)`](../tf/nn/relu_layer.md): Computes Relu(x * weight + biases).

[`sampled_softmax_loss(...)`](../tf/nn/sampled_softmax_loss.md): Computes and returns the sampled softmax training loss.

[`selu(...)`](../tf/nn/selu.md): Computes scaled exponential linear: `scale * alpha * (exp(features) - 1)`

[`separable_conv2d(...)`](../tf/nn/separable_conv2d.md): 2-D convolution with separable filters.

[`sigmoid(...)`](../tf/sigmoid.md): Computes sigmoid of `x` element-wise.

[`sigmoid_cross_entropy_with_logits(...)`](../tf/nn/sigmoid_cross_entropy_with_logits.md): Computes sigmoid cross entropy given `logits`.

[`softmax(...)`](../tf/nn/softmax.md): Computes softmax activations.

[`softmax_cross_entropy_with_logits(...)`](../tf/nn/softmax_cross_entropy_with_logits.md): Computes softmax cross entropy between `logits` and `labels`.

[`softplus(...)`](../tf/nn/softplus.md): Computes softplus: `log(exp(features) + 1)`.

[`softsign(...)`](../tf/nn/softsign.md): Computes softsign: `features / (abs(features) + 1)`.

[`sparse_softmax_cross_entropy_with_logits(...)`](../tf/nn/sparse_softmax_cross_entropy_with_logits.md): Computes sparse softmax cross entropy between `logits` and `labels`.

[`static_bidirectional_rnn(...)`](../tf/nn/static_bidirectional_rnn.md): Creates a bidirectional recurrent neural network.

[`static_rnn(...)`](../tf/nn/static_rnn.md): Creates a recurrent neural network specified by RNNCell `cell`.

[`static_state_saving_rnn(...)`](../tf/nn/static_state_saving_rnn.md): RNN that accepts a state saver for time-truncated RNN calculation.

[`sufficient_statistics(...)`](../tf/nn/sufficient_statistics.md): Calculate the sufficient statistics for the mean and variance of `x`.

[`tanh(...)`](../tf/tanh.md): Computes hyperbolic tangent of `x` element-wise.

[`top_k(...)`](../tf/nn/top_k.md): Finds values and indices of the `k` largest entries for the last dimension.

[`uniform_candidate_sampler(...)`](../tf/nn/uniform_candidate_sampler.md): Samples a set of classes using a uniform base distribution.

[`weighted_cross_entropy_with_logits(...)`](../tf/nn/weighted_cross_entropy_with_logits.md): Computes a weighted cross entropy.

[`weighted_moments(...)`](../tf/nn/weighted_moments.md): Returns the frequency-weighted mean and variance of `x`.

[`with_space_to_batch(...)`](../tf/nn/with_space_to_batch.md): Performs `op` on the space-to-batch representation of `input`.

[`xw_plus_b(...)`](../tf/nn/xw_plus_b.md): Computes matmul(x, weights) + biases.

[`zero_fraction(...)`](../tf/nn/zero_fraction.md): Returns the fraction of zeros in `value`.

## Other Members

`swish`

