<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.TPUConfig" />
<meta itemprop="property" content="iterations_per_loop"/>
<meta itemprop="property" content="num_shards"/>
<meta itemprop="property" content="per_host_input_for_training"/>
<meta itemprop="property" content="tpu_job_name"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.contrib.tpu.TPUConfig

## Class `TPUConfig`





Defined in [`tensorflow/contrib/tpu/python/tpu/tpu_config.py`](https://www.tensorflow.org/code/tensorflow/contrib/tpu/python/tpu/tpu_config.py).

TPU related configuration required by `TPUEstimator`.

#### Args:

* <b>`iterations_per_loop`</b>: This is the number of train steps runnining in TPU
    system before returning to CPU host for each `Session.run`. This means
    global step is increased `iterations_per_loop` times in one `Session.run`.
    It is recommended to be set as number of global steps for next checkpoint.
* <b>`num_shards`</b>: The number of TPU shards in the system.
* <b>`per_host_input_for_training`</b>: If `True`, `input_fn` is invoked Per-Host
    rather than Per-Core. With Per-Host input pipeline deployment, `input_fn`
    is invoked once on each host. To be precise, with a global batch size
    `train_batch_size` in `TPUEstimator` constructor, the batch size for each
    shard is `train_batch_size` // #hosts. With Per-Core input pipeline
    deployment, the shard batch size is `train_batch_size` // #cores.  Note
    that this only works for single-host TPU training now (tracked in
    b/67051042). For multi-host, please use Per-Core, i.e., `False` for
    `per_host_input_for_training`.
* <b>`tpu_job_name`</b>: The name of the TPU job. Typically, this name is auto-inferred
    within TPUEstimator, however when using ClusterSpec propagation in more
    esoteric cluster configurations, you may need to specify the job name as a
    string.

## Properties

<h3 id="iterations_per_loop"><code>iterations_per_loop</code></h3>

Alias for field number 0

<h3 id="num_shards"><code>num_shards</code></h3>

Alias for field number 1

<h3 id="per_host_input_for_training"><code>per_host_input_for_training</code></h3>

Alias for field number 2

<h3 id="tpu_job_name"><code>tpu_job_name</code></h3>

Alias for field number 3



## Methods

<h3 id="__new__"><code>__new__</code></h3>

``` python
@staticmethod
__new__(
    cls,
    iterations_per_loop=2,
    num_shards=2,
    per_host_input_for_training=True,
    tpu_job_name=None
)
```





