<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.selu" />
</div>

# tf.keras.activations.selu

``` python
selu(x)
```



Defined in [`tensorflow/python/keras/_impl/keras/activations.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/activations.py).

Scaled Exponential Linear Unit. (Klambauer et al., 2017).

#### Arguments:

* <b>`x`</b>: A tensor or variable to compute the activation function for.


#### Returns:

  Tensor with the same shape and dtype as `x`.

References:
    - [Self-Normalizing Neural Networks](https://arxiv.org/abs/1706.02515)