<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.zero_initializer" />
</div>

# tf.contrib.framework.zero_initializer

``` python
zero_initializer(
    ref,
    use_locking=True,
    name='zero_initializer'
)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/variables.py).

See the guide: [Framework (contrib) > Variables](../../../../../api_guides/python/contrib.framework.md#Variables)

Initialize 'ref' with all zeros, ref tensor should be uninitialized.
If already initialized, you will get ValueError. This op is intended to
save memory during initialization.
#### Args:

* <b>`ref`</b>: ref of the tensor need to be zero initialized.
* <b>`name`</b>: optional name for this operation.

#### Returns:

ref that initialized.

#### Raises:

* <b>`ValueError`</b>: If ref tensor is initialized.