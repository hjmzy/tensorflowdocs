<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.graph_util.convert_variables_to_constants" />
</div>

# tf.graph_util.convert_variables_to_constants

``` python
convert_variables_to_constants(
    sess,
    input_graph_def,
    output_node_names,
    variable_names_whitelist=None,
    variable_names_blacklist=None
)
```



Defined in [`tensorflow/python/framework/graph_util_impl.py`](https://www.tensorflow.org/code/tensorflow/python/framework/graph_util_impl.py).

Replaces all the variables in a graph with constants of the same values.

If you have a trained graph containing Variable ops, it can be convenient to
convert them all to Const ops holding the same values. This makes it possible
to describe the network fully with a single GraphDef file, and allows the
removal of a lot of ops related to loading and saving the variables.

#### Args:

* <b>`sess`</b>: Active TensorFlow session containing the variables.
* <b>`input_graph_def`</b>: GraphDef object holding the network.
* <b>`output_node_names`</b>: List of name strings for the result nodes of the graph.
* <b>`variable_names_whitelist`</b>: The set of variable names to convert (by default,
                            all variables are converted).
* <b>`variable_names_blacklist`</b>: The set of variable names to omit converting
                            to constants.


#### Returns:

GraphDef containing a simplified version of the original.