<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.datasets.mnist.load_data" />
</div>

# tf.keras.datasets.mnist.load_data

``` python
load_data(path='mnist.npz')
```



Defined in [`tensorflow/python/keras/_impl/keras/datasets/mnist.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/datasets/mnist.py).

Loads the MNIST dataset.

#### Arguments:

* <b>`path`</b>: path where to cache the dataset locally
        (relative to ~/.keras/datasets).


#### Returns:

Tuple of Numpy arrays: `(x_train, y_train), (x_test, y_test)`.