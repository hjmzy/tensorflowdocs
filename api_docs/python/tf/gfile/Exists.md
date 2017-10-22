<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.gfile.Exists" />
</div>

# tf.gfile.Exists

``` python
Exists(filename)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](https://www.tensorflow.org/code/tensorflow/python/lib/io/file_io.py).

Determines whether a path exists or not.

#### Args:

* <b>`filename`</b>: string, a path


#### Returns:

True if the path exists, whether its a file or a directory.
False if the path does not exist and there are no filesystem errors.


#### Raises:

* <b>`errors.OpError`</b>: Propagates any errors reported by the FileSystem API.