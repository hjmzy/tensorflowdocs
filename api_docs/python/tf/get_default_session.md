<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.get_default_session" />
</div>

# tf.get_default_session

``` python
get_default_session()
```



Defined in [`tensorflow/python/framework/ops.py`](https://www.tensorflow.org/code/tensorflow/python/framework/ops.py).

See the guide: [Running Graphs > Session management](../../../api_guides/python/client.md#Session_management)

Returns the default session for the current thread.

The returned `Session` will be the innermost session on which a
`Session` or `Session.as_default()` context has been entered.

NOTE: The default session is a property of the current thread. If you
create a new thread, and wish to use the default session in that
thread, you must explicitly add a `with sess.as_default():` in that
thread's function.

#### Returns:

The default `Session` being used in the current thread.