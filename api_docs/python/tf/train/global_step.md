<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.global_step" />
</div>

# tf.train.global_step

``` python
global_step(
    sess,
    global_step_tensor
)
```



Defined in [`tensorflow/python/training/training_util.py`](https://www.tensorflow.org/code/tensorflow/python/training/training_util.py).

See the guide: [Training > Training Utilities](../../../../api_guides/python/train.md#Training_Utilities)

Small helper to get the global step.

```python
# Creates a variable to hold the global_step.
global_step_tensor = tf.Variable(10, trainable=False, name='global_step')
# Creates a session.
sess = tf.Session()
# Initializes the variable.
print('global_step: %s' % tf.train.global_step(sess, global_step_tensor))

global_step: 10
```

#### Args:

* <b>`sess`</b>: A TensorFlow `Session` object.
* <b>`global_step_tensor`</b>:  `Tensor` or the `name` of the operation that contains
    the global step.


#### Returns:

The global step value.