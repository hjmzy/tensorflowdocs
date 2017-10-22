<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initialize_variables" />
</div>

# tf.initialize_variables

``` python
initialize_variables(
    var_list,
    name='init'
)
```



Defined in [`tensorflow/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/python/ops/variables.py).

See the guide: [Variables > Exporting and Importing Meta Graphs](../../../api_guides/python/state_ops.md#Exporting_and_Importing_Meta_Graphs)

See `tf.variables_initializer`. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed after 2017-03-02.
Instructions for updating:
Use `tf.variables_initializer` instead.

  **NOTE** The output of this function should be used.  If it is not, a warning will be logged.  To mark the output as used, call its .mark_used() method.