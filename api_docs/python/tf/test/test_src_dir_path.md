<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.test.test_src_dir_path" />
</div>

# tf.test.test_src_dir_path

``` python
test_src_dir_path(relative_path)
```



Defined in [`tensorflow/python/platform/test.py`](https://www.tensorflow.org/code/tensorflow/python/platform/test.py).

See the guide: [Testing > Unit tests](../../../../api_guides/python/test.md#Unit_tests)

Creates an absolute test srcdir path given a relative path.

#### Args:

* <b>`relative_path`</b>: a path relative to tensorflow root.
    e.g. "core/platform".


#### Returns:

An absolute path to the linked in runfiles.