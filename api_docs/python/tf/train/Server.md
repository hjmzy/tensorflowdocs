<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.Server" />
<meta itemprop="property" content="server_def"/>
<meta itemprop="property" content="target"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="create_local_server"/>
<meta itemprop="property" content="join"/>
<meta itemprop="property" content="start"/>
</div>

# tf.train.Server

## Class `Server`





Defined in [`tensorflow/python/training/server_lib.py`](https://www.tensorflow.org/code/tensorflow/python/training/server_lib.py).

See the guide: [Training > Distributed execution](../../../../api_guides/python/train.md#Distributed_execution)

An in-process TensorFlow server, for use in distributed training.

A `tf.train.Server` instance encapsulates a set of devices and a
[`tf.Session`](../../tf/Session.md) target that
can participate in distributed training. A server belongs to a
cluster (specified by a [`tf.train.ClusterSpec`](../../tf/train/ClusterSpec.md)), and
corresponds to a particular task in a named job. The server can
communicate with any other server in the same cluster.

## Properties

<h3 id="server_def"><code>server_def</code></h3>

Returns the `tf.train.ServerDef` for this server.

#### Returns:

A `tf.train.ServerDef` protocol buffer that describes the configuration
of this server.

<h3 id="target"><code>target</code></h3>

Returns the target for a `tf.Session` to connect to this server.

To create a
[`tf.Session`](../../tf/Session.md) that
connects to this server, use the following snippet:

```python
server = tf.train.Server(...)
with tf.Session(server.target):
  # ...
```

#### Returns:

A string containing a session target for this server.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    server_or_cluster_def,
    job_name=None,
    task_index=None,
    protocol=None,
    config=None,
    start=True
)
```

Creates a new server with the given definition.

The `job_name`, `task_index`, and `protocol` arguments are optional, and
override any information provided in `server_or_cluster_def`.

#### Args:

* <b>`server_or_cluster_def`</b>: A `tf.train.ServerDef` or
    `tf.train.ClusterDef` protocol buffer, or a
    `tf.train.ClusterSpec` object, describing the server to be
    created and/or the cluster of which it is a member.
* <b>`job_name`</b>: (Optional.) Specifies the name of the job of which the server
    is a member. Defaults to the value in `server_or_cluster_def`, if
    specified.
* <b>`task_index`</b>: (Optional.) Specifies the task index of the server in its
    job. Defaults to the value in `server_or_cluster_def`, if specified.
    Otherwise defaults to 0 if the server's job has only one task.
* <b>`protocol`</b>: (Optional.) Specifies the protocol to be used by the server.
    Acceptable values include `"grpc"`. Defaults to the value in
    `server_or_cluster_def`, if specified. Otherwise defaults to `"grpc"`.
* <b>`config`</b>: (Options.) A `tf.ConfigProto` that specifies default
    configuration options for all sessions that run on this server.
* <b>`start`</b>: (Optional.) Boolean, indicating whether to start the server
    after creating it. Defaults to `True`.


#### Raises:

* <b>`tf.errors.OpError`</b>: Or one of its subclasses if an error occurs while
    creating the TensorFlow server.

<h3 id="create_local_server"><code>create_local_server</code></h3>

``` python
@staticmethod
create_local_server(
    config=None,
    start=True
)
```

Creates a new single-process cluster running on the local host.

This method is a convenience wrapper for creating a
`tf.train.Server` with a `tf.train.ServerDef` that specifies a
single-process cluster containing a single task in a job called
`"local"`.

#### Args:

* <b>`config`</b>: (Options.) A `tf.ConfigProto` that specifies default
    configuration options for all sessions that run on this server.
* <b>`start`</b>: (Optional.) Boolean, indicating whether to start the server after
    creating it. Defaults to `True`.


#### Returns:

A local `tf.train.Server`.

<h3 id="join"><code>join</code></h3>

``` python
join()
```

Blocks until the server has shut down.

This method currently blocks forever.

#### Raises:

* <b>`tf.errors.OpError`</b>: Or one of its subclasses if an error occurs while
    joining the TensorFlow server.

<h3 id="start"><code>start</code></h3>

``` python
start()
```

Starts this server.

#### Raises:

* <b>`tf.errors.OpError`</b>: Or one of its subclasses if an error occurs while
    starting the TensorFlow server.



