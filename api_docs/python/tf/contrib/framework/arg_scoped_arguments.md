<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.arg_scoped_arguments" />
</div>

# tf.contrib.framework.arg_scoped_arguments

``` python
arg_scoped_arguments(func)
```



Defined in [`tensorflow/contrib/framework/python/ops/arg_scope.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/arg_scope.py).

See the guide: [Framework (contrib) > Arg_Scope](../../../../../api_guides/python/contrib.framework.md#Arg_Scope)

Returns the list kwargs that arg_scope can set for a func.

#### Args:

* <b>`func`</b>: function which has been decorated with @add_arg_scope.


#### Returns:

a list of kwargs names.