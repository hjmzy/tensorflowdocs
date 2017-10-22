<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.signal.inverse_stft" />
</div>

# tf.contrib.signal.inverse_stft

``` python
inverse_stft(
    stfts,
    frame_length,
    frame_step,
    fft_length=None,
    window_fn=functools.partial(window_ops.hann_window, periodic=True),
    name=None
)
```



Defined in [`tensorflow/contrib/signal/python/ops/spectral_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/signal/python/ops/spectral_ops.py).

Computes the inverse [Short-time Fourier Transform][stft] of `stfts`.

Implemented with GPU-compatible ops and supports gradients.

#### Args:

* <b>`stfts`</b>: A `complex64` `[..., frames, fft_unique_bins]` `Tensor` of STFT bins
    representing a batch of `fft_length`-point STFTs where `fft_unique_bins`
    is `fft_length // 2 + 1`
* <b>`frame_length`</b>: An integer scalar `Tensor`. The window length in samples.
* <b>`frame_step`</b>: An integer scalar `Tensor`. The number of samples to step.
* <b>`fft_length`</b>: An integer scalar `Tensor`. The size of the FFT that produced
    `stfts`. If not provided, uses the smallest power of 2 enclosing
    `frame_length`.
* <b>`window_fn`</b>: A callable that takes a window length and a `dtype` keyword
    argument and returns a `[window_length]` `Tensor` of samples in the
    provided datatype. If set to `None`, no windowing is used.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `[..., samples]` `Tensor` of `float32` signals representing the inverse
STFT for each input STFT in `stfts`.


#### Raises:

* <b>`ValueError`</b>: If `stfts` is not at least rank 2, `frame_length` is not scalar,
    `frame_step` is not scalar, or `fft_length` is not scalar.

[stft]: https://en.wikipedia.org/wiki/Short-time_Fourier_transform