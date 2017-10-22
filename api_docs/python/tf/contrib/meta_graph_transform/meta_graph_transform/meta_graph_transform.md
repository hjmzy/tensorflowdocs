<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.meta_graph_transform.meta_graph_transform.meta_graph_transform" />
</div>

# tf.contrib.meta_graph_transform.meta_graph_transform.meta_graph_transform

``` python
meta_graph_transform(
    base_meta_graph_def,
    input_names,
    output_names,
    transforms,
    tags,
    checkpoint_path=None
)
```



Defined in [`tensorflow/contrib/meta_graph_transform/meta_graph_transform.py`](https://www.tensorflow.org/code/tensorflow/contrib/meta_graph_transform/meta_graph_transform.py).

Apply the Graph Transform tool to a MetaGraphDef.

#### Args:

* <b>`base_meta_graph_def`</b>: A MetaGraphDef protocol buffer to transform.
* <b>`input_names`</b>: Names of input nodes.
* <b>`output_names`</b>: Names of output nodes.
* <b>`transforms`</b>: A list of strings naming the graph transforms to be applied in
    order.  These transform names are exactly those supported by the Graph
    Transform Tool, with the addition of the 'freeze_graph' and
    'sparsify_gather' transforms.
* <b>`tags`</b>: A list of tags with which to annotate the transformed MetaGraphDef.
* <b>`checkpoint_path`</b>: A path to a checkpoint to restore during freezing,
    if needed (default None).


#### Returns:

A new transformed MetaGraphDef protocol buffer.