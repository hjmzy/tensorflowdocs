<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.avg_pool3d" />
</div>

# tf.nn.avg_pool3d

``` python
avg_pool3d(
    input,
    ksize,
    strides,
    padding,
    data_format='NDHWC',
    name=None
)
```



Defined in `tensorflow/python/ops/gen_nn_ops.py`.

See the guide: [Neural Network > Pooling](../../../../api_guides/python/nn.md#Pooling)

Performs 3D average pooling on the input.

#### Args:

* <b>`input`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`.
    Shape `[batch, depth, rows, cols, channels]` tensor to pool over.
* <b>`ksize`</b>: A list of `ints` that has length `>= 5`.
    1-D tensor of length 5. The size of the window for each dimension of
    the input tensor. Must have `ksize[0] = ksize[4] = 1`.
* <b>`strides`</b>: A list of `ints` that has length `>= 5`.
    1-D tensor of length 5. The stride of the sliding window for each
    dimension of `input`. Must have `strides[0] = strides[4] = 1`.
* <b>`padding`</b>: A `string` from: `"SAME", "VALID"`.
    The type of padding algorithm to use.
* <b>`data_format`</b>: An optional `string` from: `"NDHWC", "NCDHW"`. Defaults to `"NDHWC"`.
    The data format of the input and output data. With the
    default format "NDHWC", the data is stored in the order of:
        [batch, in_depth, in_height, in_width, in_channels].
    Alternatively, the format could be "NCDHW", the data storage order is:
        [batch, in_channels, in_depth, in_height, in_width].
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.
The average pooled output tensor.