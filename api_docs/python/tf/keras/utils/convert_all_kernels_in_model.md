<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.convert_all_kernels_in_model" />
</div>

# tf.keras.utils.convert_all_kernels_in_model

``` python
convert_all_kernels_in_model(model)
```



Defined in [`tensorflow/python/keras/_impl/keras/utils/layer_utils.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/utils/layer_utils.py).

Converts all convolution kernels in a model from Theano to TensorFlow.

Also works from TensorFlow to Theano.

#### Arguments:

* <b>`model`</b>: target model for the conversion.