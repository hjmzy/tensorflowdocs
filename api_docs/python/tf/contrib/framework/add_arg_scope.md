<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.add_arg_scope" />
</div>

# tf.contrib.framework.add_arg_scope

``` python
add_arg_scope(func)
```



Defined in [`tensorflow/contrib/framework/python/ops/arg_scope.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/arg_scope.py).

See the guide: [Framework (contrib) > Arg_Scope](../../../../../api_guides/python/contrib.framework.md#Arg_Scope)

Decorates a function with args so it can be used within an arg_scope.

#### Args:

* <b>`func`</b>: function to decorate.


#### Returns:

A tuple with the decorated function func_with_args().