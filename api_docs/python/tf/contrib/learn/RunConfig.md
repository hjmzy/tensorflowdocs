<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.learn.RunConfig" />
<meta itemprop="property" content="cluster_spec"/>
<meta itemprop="property" content="environment"/>
<meta itemprop="property" content="evaluation_master"/>
<meta itemprop="property" content="is_chief"/>
<meta itemprop="property" content="keep_checkpoint_every_n_hours"/>
<meta itemprop="property" content="keep_checkpoint_max"/>
<meta itemprop="property" content="log_step_count_steps"/>
<meta itemprop="property" content="master"/>
<meta itemprop="property" content="model_dir"/>
<meta itemprop="property" content="num_ps_replicas"/>
<meta itemprop="property" content="num_worker_replicas"/>
<meta itemprop="property" content="save_checkpoints_secs"/>
<meta itemprop="property" content="save_checkpoints_steps"/>
<meta itemprop="property" content="save_summary_steps"/>
<meta itemprop="property" content="service"/>
<meta itemprop="property" content="session_config"/>
<meta itemprop="property" content="task_id"/>
<meta itemprop="property" content="task_type"/>
<meta itemprop="property" content="tf_config"/>
<meta itemprop="property" content="tf_random_seed"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="get_task_id"/>
<meta itemprop="property" content="replace"/>
<meta itemprop="property" content="uid"/>
</div>

# tf.contrib.learn.RunConfig

## Class `RunConfig`

Inherits From: [`RunConfig`](../../../tf/estimator/RunConfig.md)



Defined in [`tensorflow/contrib/learn/python/learn/estimators/run_config.py`](https://www.tensorflow.org/code/tensorflow/contrib/learn/python/learn/estimators/run_config.py).

See the guide: [Learn (contrib) > Graph actions](../../../../../api_guides/python/contrib.learn.md#Graph_actions)

This class specifies the configurations for an `Estimator` run.

This class is the implementation of [`tf.estimator.RunConfig`](../../../tf/estimator/RunConfig.md) interface.

## Properties

<h3 id="cluster_spec"><code>cluster_spec</code></h3>



<h3 id="environment"><code>environment</code></h3>



<h3 id="evaluation_master"><code>evaluation_master</code></h3>



<h3 id="is_chief"><code>is_chief</code></h3>



<h3 id="keep_checkpoint_every_n_hours"><code>keep_checkpoint_every_n_hours</code></h3>



<h3 id="keep_checkpoint_max"><code>keep_checkpoint_max</code></h3>



<h3 id="log_step_count_steps"><code>log_step_count_steps</code></h3>



<h3 id="master"><code>master</code></h3>



<h3 id="model_dir"><code>model_dir</code></h3>



<h3 id="num_ps_replicas"><code>num_ps_replicas</code></h3>



<h3 id="num_worker_replicas"><code>num_worker_replicas</code></h3>



<h3 id="save_checkpoints_secs"><code>save_checkpoints_secs</code></h3>



<h3 id="save_checkpoints_steps"><code>save_checkpoints_steps</code></h3>



<h3 id="save_summary_steps"><code>save_summary_steps</code></h3>



<h3 id="service"><code>service</code></h3>

Returns the platform defined (in TF_CONFIG) service dict.

<h3 id="session_config"><code>session_config</code></h3>



<h3 id="task_id"><code>task_id</code></h3>



<h3 id="task_type"><code>task_type</code></h3>



<h3 id="tf_config"><code>tf_config</code></h3>



<h3 id="tf_random_seed"><code>tf_random_seed</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    master=None,
    num_cores=0,
    log_device_placement=False,
    gpu_memory_fraction=1,
    tf_random_seed=None,
    save_summary_steps=100,
    save_checkpoints_secs=_USE_DEFAULT,
    save_checkpoints_steps=None,
    keep_checkpoint_max=5,
    keep_checkpoint_every_n_hours=10000,
    log_step_count_steps=100,
    evaluation_master='',
    model_dir=None,
    session_config=None
)
```

Constructor.

The superclass `ClusterConfig` may set properties like `cluster_spec`,
`is_chief`, `master` (if `None` in the args), `num_ps_replicas`, `task_id`,
and `task_type` based on the `TF_CONFIG` environment variable. See
`ClusterConfig` for more details.

N.B.: If `save_checkpoints_steps` or `save_checkpoints_secs` is set,
`keep_checkpoint_max` might need to be adjusted accordingly, especially in
distributed training. For example, setting `save_checkpoints_secs` as 60
without adjusting `keep_checkpoint_max` (defaults to 5) leads to situation
that checkpoint would be garbage collected after 5 minutes. In distributed
training, the evaluation job starts asynchronously and might fail to load or
find the checkpoint due to race condition.

#### Args:

* <b>`master`</b>: TensorFlow master. Defaults to empty string for local.
* <b>`num_cores`</b>: Number of cores to be used. If 0, the system picks an
    appropriate number (default: 0).
* <b>`log_device_placement`</b>: Log the op placement to devices (default: False).
* <b>`gpu_memory_fraction`</b>: Fraction of GPU memory used by the process on
    each GPU uniformly on the same machine.
* <b>`tf_random_seed`</b>: Random seed for TensorFlow initializers.
    Setting this value allows consistency between reruns.
* <b>`save_summary_steps`</b>: Save summaries every this many steps.
* <b>`save_checkpoints_secs`</b>: Save checkpoints every this many seconds. Can not
      be specified with `save_checkpoints_steps`.
* <b>`save_checkpoints_steps`</b>: Save checkpoints every this many steps. Can not be
      specified with `save_checkpoints_secs`.
* <b>`keep_checkpoint_max`</b>: The maximum number of recent checkpoint files to
    keep. As new files are created, older files are deleted. If None or 0,
    all checkpoint files are kept. Defaults to 5 (that is, the 5 most recent
    checkpoint files are kept.)
* <b>`keep_checkpoint_every_n_hours`</b>: Number of hours between each checkpoint
    to be saved. The default value of 10,000 hours effectively disables
    the feature.
* <b>`log_step_count_steps`</b>: The frequency, in number of global steps, that the
    global step/sec will be logged during training.
* <b>`evaluation_master`</b>: the master on which to perform evaluation.
* <b>`model_dir`</b>: directory where model parameters, graph etc are saved. If
    `None`, will use `model_dir` property in `TF_CONFIG` environment
    variable. If both are set, must have same value. If both are `None`, see
    `Estimator` about where the model will be saved.
* <b>`session_config`</b>: a ConfigProto used to set session parameters, or None.
    Note - using this argument, it is easy to provide settings which break
    otherwise perfectly good models. Use with care.

<h3 id="get_task_id"><code>get_task_id</code></h3>

``` python
get_task_id()
```

Returns task index from `TF_CONFIG` environmental variable.

If you have a ClusterConfig instance, you can just access its task_id
property instead of calling this function and re-parsing the environmental
variable.

#### Returns:

`TF_CONFIG['task']['index']`. Defaults to 0.

<h3 id="replace"><code>replace</code></h3>

``` python
replace(**kwargs)
```

Returns a new instance of `RunConfig` replacing specified properties.

Only the properties in the following list are allowed to be replaced:
  - `model_dir`.
  - `tf_random_seed`,
  - `save_summary_steps`,
  - `save_checkpoints_steps`,
  - `save_checkpoints_secs`,
  - `session_config`,
  - `keep_checkpoint_max`,
  - `keep_checkpoint_every_n_hours`,
  - `log_step_count_steps`,

In addition, either `save_checkpoints_steps` or `save_checkpoints_secs`
can be set (should not be both).

#### Args:

* <b>`**kwargs`</b>: keyword named properties with new values.


#### Raises:

* <b>`ValueError`</b>: If any property name in `kwargs` does not exist or is not
    allowed to be replaced, or both `save_checkpoints_steps` and
    `save_checkpoints_secs` are set.


#### Returns:

a new instance of `RunConfig`.

<h3 id="uid"><code>uid</code></h3>

``` python
uid(
    *args,
    **kwargs
)
```

Generates a 'Unique Identifier' based on all internal fields. (experimental)

THIS FUNCTION IS EXPERIMENTAL. It may change or be removed at any time, and without warning.


Caller should use the uid string to check `RunConfig` instance integrity
in one session use, but should not rely on the implementation details, which
is subject to change.

#### Args:

* <b>`whitelist`</b>: A list of the string names of the properties uid should not
    include. If `None`, defaults to `_DEFAULT_UID_WHITE_LIST`, which
    includes most properties user allowes to change.


#### Returns:

A uid string.



