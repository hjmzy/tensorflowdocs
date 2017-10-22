<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.gfile.Remove" />
</div>

# tf.gfile.Remove

``` python
Remove(filename)
```



Defined in [`tensorflow/python/lib/io/file_io.py`](https://www.tensorflow.org/code/tensorflow/python/lib/io/file_io.py).

Deletes the file located at 'filename'.

#### Args:

* <b>`filename`</b>: string, a filename


#### Raises:

* <b>`errors.OpError`</b>: Propagates any errors reported by the FileSystem API.  E.g.,
  NotFoundError if the file does not exist.