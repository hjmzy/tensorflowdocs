<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.resource_loader.load_resource" />
</div>

# tf.resource_loader.load_resource

``` python
load_resource(path)
```



Defined in [`tensorflow/python/platform/resource_loader.py`](https://www.tensorflow.org/code/tensorflow/python/platform/resource_loader.py).

Load the resource at given path, where path is relative to tensorflow/.

#### Args:

* <b>`path`</b>: a string resource path relative to tensorflow/.


#### Returns:

The contents of that resource.


#### Raises:

* <b>`IOError`</b>: If the path is not found, or the resource can't be opened.