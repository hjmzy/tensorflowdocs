<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.signal" />
</div>

# Module: tf.contrib.signal



Defined in [`tensorflow/contrib/signal/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/signal/__init__.py).

Signal processing operations.

See the [Signal Processing (contrib)](../../../../api_guides/python/contrib.signal.md) guide.


[hamming]: https://en.wikipedia.org/wiki/Window_function#Hamming_window
[hann]: https://en.wikipedia.org/wiki/Window_function#Hann_window
[mel]: https://en.wikipedia.org/wiki/Mel_scale
[mfcc]: https://en.wikipedia.org/wiki/Mel-frequency_cepstrum
[stft]: https://en.wikipedia.org/wiki/Short-time_Fourier_transform

## Functions

[`frame(...)`](../../tf/contrib/signal/frame.md): Expands `signal`'s `axis` dimension into frames of `frame_length`.

[`hamming_window(...)`](../../tf/contrib/signal/hamming_window.md): Generate a [Hamming][hamming] window.

[`hann_window(...)`](../../tf/contrib/signal/hann_window.md): Generate a [Hann window][hann].

[`inverse_stft(...)`](../../tf/contrib/signal/inverse_stft.md): Computes the inverse [Short-time Fourier Transform][stft] of `stfts`.

[`linear_to_mel_weight_matrix(...)`](../../tf/contrib/signal/linear_to_mel_weight_matrix.md): Returns a matrix to warp linear scale spectrograms to the [mel scale][mel].

[`mfccs_from_log_mel_spectrograms(...)`](../../tf/contrib/signal/mfccs_from_log_mel_spectrograms.md): Computes [MFCCs][mfcc] of `log_mel_spectrograms`.

[`overlap_and_add(...)`](../../tf/contrib/signal/overlap_and_add.md): Reconstructs a signal from a framed representation.

[`stft(...)`](../../tf/contrib/signal/stft.md): Computes the [Short-time Fourier Transform][stft] of `signals`.

