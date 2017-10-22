<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ifft" />
</div>

# tf.ifft

### Aliases:

* `tf.ifft`
* `tf.spectral.ifft`

``` python
ifft(
    input,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_spectral_ops.py`.

See the guide: [Spectral Functions > Discrete Fourier Transforms](../../../api_guides/python/spectral_ops.md#Discrete_Fourier_Transforms)

Inverse fast Fourier transform.

Computes the inverse 1-dimensional discrete Fourier transform over the
inner-most dimension of `input`.

#### Args:

* <b>`input`</b>: A `Tensor` of type `complex64`. A complex64 tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `complex64`.
A complex64 tensor of the same shape as `input`. The inner-most
  dimension of `input` is replaced with its inverse 1D Fourier transform.



#### numpy compatibility
  Equivalent to np.fft.ifft

