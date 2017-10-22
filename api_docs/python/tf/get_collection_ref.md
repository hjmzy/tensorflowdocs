<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.get_collection_ref" />
</div>

# tf.get_collection_ref

``` python
get_collection_ref(key)
```



Defined in [`tensorflow/python/framework/ops.py`](https://www.tensorflow.org/code/tensorflow/python/framework/ops.py).

See the guide: [Building Graphs > Graph collections](../../../api_guides/python/framework.md#Graph_collections)

Wrapper for `Graph.get_collection_ref()` using the default graph.

See [`tf.Graph.get_collection_ref`](../tf/Graph.md#get_collection_ref)
for more details.

#### Args:

* <b>`key`</b>: The key for the collection. For example, the `GraphKeys` class
    contains many standard names for collections.


#### Returns:

The list of values in the collection with the given `name`, or an empty
list if no value has been added to that collection.  Note that this returns
the collection list itself, which can be modified in place to change the
collection.