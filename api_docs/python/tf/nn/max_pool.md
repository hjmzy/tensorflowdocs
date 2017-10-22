<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.max_pool" />
</div>

# tf.nn.max_pool

``` python
max_pool(
    value,
    ksize,
    strides,
    padding,
    data_format='NHWC',
    name=None
)
```



Defined in [`tensorflow/python/ops/nn_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/nn_ops.py).

See the guide: [Neural Network > Pooling](../../../../api_guides/python/nn.md#Pooling)

Performs the max pooling on the input.

#### Args:

* <b>`value`</b>: A 4-D `Tensor` of the format specified by `data_format`.
* <b>`ksize`</b>: A 1-D int Tensor of 4 elements.  The size of the window for
    each dimension of the input tensor.
* <b>`strides`</b>: A 1-D int Tensor of 4 elements.  The stride of the sliding
    window for each dimension of the input tensor.
* <b>`padding`</b>: A string, either `'VALID'` or `'SAME'`. The padding algorithm.
    See the [comment here](../../tf/nn/convolution.md)
* <b>`data_format`</b>: A string. 'NHWC', 'NCHW' and 'NCHW_VECT_C' are supported.
* <b>`name`</b>: Optional name for the operation.


#### Returns:

A `Tensor` of format specified by `data_format`.
The max pooled output tensor.