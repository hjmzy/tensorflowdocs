<!-- DO NOT EDIT! Automatically generated file. -->
# Tensor Transformations

Note: Functions taking `Tensor` arguments can also take anything accepted by
[`tf.convert_to_tensor`](../../api_docs/python/tf/convert_to_tensor.md).

[TOC]

<h2 id="Casting">Casting</h2>

TensorFlow provides several operations that you can use to cast tensor data
types in your graph.

*   [`tf.string_to_number`](../../api_docs/python/tf/string_to_number.md)
*   [`tf.to_double`](../../api_docs/python/tf/to_double.md)
*   [`tf.to_float`](../../api_docs/python/tf/to_float.md)
*   [`tf.to_bfloat16`](../../api_docs/python/tf/to_bfloat16.md)
*   [`tf.to_int32`](../../api_docs/python/tf/to_int32.md)
*   [`tf.to_int64`](../../api_docs/python/tf/to_int64.md)
*   [`tf.cast`](../../api_docs/python/tf/cast.md)
*   [`tf.bitcast`](../../api_docs/python/tf/bitcast.md)
*   [`tf.saturate_cast`](../../api_docs/python/tf/saturate_cast.md)

<h2 id="Shapes_and_Shaping">Shapes and Shaping</h2>

TensorFlow provides several operations that you can use to determine the shape
of a tensor and change the shape of a tensor.

*   [`tf.broadcast_dynamic_shape`](../../api_docs/python/tf/broadcast_dynamic_shape.md)
*   [`tf.broadcast_static_shape`](../../api_docs/python/tf/broadcast_static_shape.md)
*   [`tf.shape`](../../api_docs/python/tf/shape.md)
*   [`tf.shape_n`](../../api_docs/python/tf/shape_n.md)
*   [`tf.size`](../../api_docs/python/tf/size.md)
*   [`tf.rank`](../../api_docs/python/tf/rank.md)
*   [`tf.reshape`](../../api_docs/python/tf/reshape.md)
*   [`tf.squeeze`](../../api_docs/python/tf/squeeze.md)
*   [`tf.expand_dims`](../../api_docs/python/tf/expand_dims.md)
*   [`tf.meshgrid`](../../api_docs/python/tf/meshgrid.md)

<h2 id="Slicing_and_Joining">Slicing and Joining</h2>

TensorFlow provides several operations to slice or extract parts of a tensor,
or join multiple tensors together.

*   [`tf.slice`](../../api_docs/python/tf/slice.md)
*   [`tf.strided_slice`](../../api_docs/python/tf/strided_slice.md)
*   [`tf.split`](../../api_docs/python/tf/split.md)
*   [`tf.tile`](../../api_docs/python/tf/tile.md)
*   [`tf.pad`](../../api_docs/python/tf/pad.md)
*   [`tf.concat`](../../api_docs/python/tf/concat.md)
*   [`tf.stack`](../../api_docs/python/tf/stack.md)
*   [`tf.parallel_stack`](../../api_docs/python/tf/parallel_stack.md)
*   [`tf.unstack`](../../api_docs/python/tf/unstack.md)
*   [`tf.reverse_sequence`](../../api_docs/python/tf/reverse_sequence.md)
*   [`tf.reverse`](../../api_docs/python/tf/reverse.md)
*   [`tf.reverse_v2`](../../api_docs/python/tf/reverse_v2.md)
*   [`tf.transpose`](../../api_docs/python/tf/transpose.md)
*   [`tf.extract_image_patches`](../../api_docs/python/tf/extract_image_patches.md)
*   [`tf.space_to_batch_nd`](../../api_docs/python/tf/space_to_batch_nd.md)
*   [`tf.space_to_batch`](../../api_docs/python/tf/space_to_batch.md)
*   [`tf.required_space_to_batch_paddings`](../../api_docs/python/tf/required_space_to_batch_paddings.md)
*   [`tf.batch_to_space_nd`](../../api_docs/python/tf/batch_to_space_nd.md)
*   [`tf.batch_to_space`](../../api_docs/python/tf/batch_to_space.md)
*   [`tf.space_to_depth`](../../api_docs/python/tf/space_to_depth.md)
*   [`tf.depth_to_space`](../../api_docs/python/tf/depth_to_space.md)
*   [`tf.gather`](../../api_docs/python/tf/gather.md)
*   [`tf.gather_nd`](../../api_docs/python/tf/gather_nd.md)
*   [`tf.unique_with_counts`](../../api_docs/python/tf/unique_with_counts.md)
*   [`tf.scatter_nd`](../../api_docs/python/tf/scatter_nd.md)
*   [`tf.dynamic_partition`](../../api_docs/python/tf/dynamic_partition.md)
*   [`tf.dynamic_stitch`](../../api_docs/python/tf/dynamic_stitch.md)
*   [`tf.boolean_mask`](../../api_docs/python/tf/boolean_mask.md)
*   [`tf.one_hot`](../../api_docs/python/tf/one_hot.md)
*   [`tf.sequence_mask`](../../api_docs/python/tf/sequence_mask.md)
*   [`tf.dequantize`](../../api_docs/python/tf/dequantize.md)
*   [`tf.quantize_v2`](../../api_docs/python/tf/quantize_v2.md)
*   [`tf.quantized_concat`](../../api_docs/python/tf/quantized_concat.md)
*   [`tf.setdiff1d`](../../api_docs/python/tf/setdiff1d.md)

<h2 id="Fake_quantization">Fake quantization</h2>
Operations used to help train for better quantization accuracy.

*   [`tf.fake_quant_with_min_max_args`](../../api_docs/python/tf/fake_quant_with_min_max_args.md)
*   [`tf.fake_quant_with_min_max_args_gradient`](../../api_docs/python/tf/fake_quant_with_min_max_args_gradient.md)
*   [`tf.fake_quant_with_min_max_vars`](../../api_docs/python/tf/fake_quant_with_min_max_vars.md)
*   [`tf.fake_quant_with_min_max_vars_gradient`](../../api_docs/python/tf/fake_quant_with_min_max_vars_gradient.md)
*   [`tf.fake_quant_with_min_max_vars_per_channel`](../../api_docs/python/tf/fake_quant_with_min_max_vars_per_channel.md)
*   [`tf.fake_quant_with_min_max_vars_per_channel_gradient`](../../api_docs/python/tf/fake_quant_with_min_max_vars_per_channel_gradient.md)
