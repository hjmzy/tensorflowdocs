<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.gfile.DeleteRecursively" />
</div>

# tf.gfile.DeleteRecursively

``` python
DeleteRecursively(dirname)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](https://www.tensorflow.org/code/tensorflow/python/lib/io/file_io.py).

Deletes everything under dirname recursively.

#### Args:

* <b>`dirname`</b>: string, a path to a directory


#### Raises:

* <b>`errors.OpError`</b>: If the operation fails.