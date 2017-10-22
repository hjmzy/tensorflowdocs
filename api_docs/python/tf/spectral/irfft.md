<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.spectral.irfft" />
</div>

# tf.spectral.irfft

``` python
irfft(
    input_tensor,
    fft_length=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/spectral_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/spectral_ops.py).

See the guide: [Spectral Functions > Discrete Fourier Transforms](../../../../api_guides/python/spectral_ops.md#Discrete_Fourier_Transforms)

Inverse real-valued fast Fourier transform.

Computes the inverse 1-dimensional discrete Fourier transform of a real-valued
signal over the inner-most dimension of `input`.

The inner-most dimension of `input` is assumed to be the result of `RFFT`: the
`fft_length / 2 + 1` unique components of the DFT of a real-valued signal. If
`fft_length` is not provided, it is computed from the size of the inner-most
dimension of `input` (`fft_length = 2 * (inner - 1)`). If the FFT length used to
compute `input` is odd, it should be provided since it cannot be inferred
properly.

Along the axis `IRFFT` is computed on, if `fft_length / 2 + 1` is smaller
than the corresponding dimension of `input`, the dimension is cropped. If it is
larger, the dimension is padded with zeros.

#### Args:

* <b>`input`</b>: A `Tensor` of type `complex64`. A complex64 tensor.
* <b>`fft_length`</b>: A `Tensor` of type `int32`.
    An int32 tensor of shape [1]. The FFT length.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `float32`.
A float32 tensor of the same rank as `input`. The inner-most
  dimension of `input` is replaced with the `fft_length` samples of its inverse
  1D Fourier transform.



#### numpy compatibility
  Equivalent to np.fft.irfft

