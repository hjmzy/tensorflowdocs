<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.random_normal_variable" />
</div>

# tf.keras.backend.random_normal_variable

``` python
random_normal_variable(
    shape,
    mean,
    scale,
    dtype=None,
    name=None,
    seed=None
)
```



Defined in [`tensorflow/python/keras/_impl/keras/backend.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/backend.py).

Instantiates a variable with values drawn from a normal distribution.

#### Arguments:

* <b>`shape`</b>: Tuple of integers, shape of returned Keras variable.
* <b>`mean`</b>: Float, mean of the normal distribution.
* <b>`scale`</b>: Float, standard deviation of the normal distribution.
* <b>`dtype`</b>: String, dtype of returned Keras variable.
* <b>`name`</b>: String, name of returned Keras variable.
* <b>`seed`</b>: Integer, random seed.


#### Returns:

    A Keras variable, filled with drawn samples.

Example:
```python
    # TensorFlow example
    >>> kvar = K.random_normal_variable((2,3), 0, 1)
    >>> kvar
    <tensorflow.python.ops.variables.Variable object at 0x10ab12dd0>
    >>> K.eval(kvar)
    array([[ 1.19591331,  0.68685907, -0.63814116],
           [ 0.92629528,  0.28055015,  1.70484698]], dtype=float32)
```