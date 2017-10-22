<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.moments" />
</div>

# tf.nn.moments

``` python
moments(
    x,
    axes,
    shift=None,
    name=None,
    keep_dims=False
)
```



Defined in [`tensorflow/python/ops/nn_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/nn_impl.py).

See the guide: [Neural Network > Normalization](../../../../api_guides/python/nn.md#Normalization)

Calculate the mean and variance of `x`.

The mean and variance are calculated by aggregating the contents of `x`
across `axes`.  If `x` is 1-D and `axes = [0]` this is just the mean
and variance of a vector.

Note: shift is currently not used, the true mean is computed and used.

When using these moments for batch normalization (see
`tf.nn.batch_normalization`):

 * for so-called "global normalization", used with convolutional filters with
   shape `[batch, height, width, depth]`, pass `axes=[0, 1, 2]`.
 * for simple batch normalization pass `axes=[0]` (batch only).

#### Args:

* <b>`x`</b>: A `Tensor`.
* <b>`axes`</b>: Array of ints.  Axes along which to compute mean and
    variance.
* <b>`shift`</b>: Not used in the current implementation
* <b>`name`</b>: Name used to scope the operations that compute the moments.
* <b>`keep_dims`</b>: produce moments with the same dimensionality as the input.


#### Returns:

Two `Tensor` objects: `mean` and `variance`.