<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.relu_layer" />
</div>

# tf.nn.relu_layer

``` python
relu_layer(
    x,
    weights,
    biases,
    name=None
)
```



Defined in [`tensorflow/python/ops/nn_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/nn_impl.py).

Computes Relu(x * weight + biases).

#### Args:

* <b>`x`</b>: a 2D tensor.  Dimensions typically: batch, in_units
* <b>`weights`</b>: a 2D tensor.  Dimensions typically: in_units, out_units
* <b>`biases`</b>: a 1D tensor.  Dimensions: out_units
* <b>`name`</b>: A name for the operation (optional).  If not specified
    "nn_relu_layer" is used.


#### Returns:

A 2-D Tensor computing relu(matmul(x, weights) + biases).
Dimensions typically: batch, out_units.