<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.training.StopAfterNEvalsHook" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="after_create_session"/>
<meta itemprop="property" content="after_run"/>
<meta itemprop="property" content="before_run"/>
<meta itemprop="property" content="begin"/>
<meta itemprop="property" content="end"/>
</div>

# tf.contrib.training.StopAfterNEvalsHook

## Class `StopAfterNEvalsHook`

Inherits From: [`SessionRunHook`](../../../tf/train/SessionRunHook.md)



Defined in [`tensorflow/python/training/evaluation.py`](https://www.tensorflow.org/code/tensorflow/python/training/evaluation.py).

Run hook used by the evaluation routines to run the `eval_ops` N times.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    num_evals,
    log_progress=True
)
```

Constructs the run hook.

#### Args:

* <b>`num_evals`</b>: The number of evaluations to run for. if set to None, will
    iterate the dataset until all inputs are exhausted.
* <b>`log_progress`</b>: Whether to log evaluation progress, defaults to True.

<h3 id="after_create_session"><code>after_create_session</code></h3>

``` python
after_create_session(
    session,
    coord
)
```

Called when new TensorFlow session is created.

This is called to signal the hooks that a new session has been created. This
has two essential differences with the situation in which `begin` is called:

* When this is called, the graph is finalized and ops can no longer be added
    to the graph.
* This method will also be called as a result of recovering a wrapped
    session, not only at the beginning of the overall session.

#### Args:

* <b>`session`</b>: A TensorFlow Session that has been created.
* <b>`coord`</b>: A Coordinator object which keeps track of all threads.

<h3 id="after_run"><code>after_run</code></h3>

``` python
after_run(
    run_context,
    run_values
)
```



<h3 id="before_run"><code>before_run</code></h3>

``` python
before_run(run_context)
```



<h3 id="begin"><code>begin</code></h3>

``` python
begin()
```

Called once before using the session.

When called, the default graph is the one that will be launched in the
session.  The hook can modify the graph by adding new operations to it.
After the `begin()` call the graph will be finalized and the other callbacks
can not modify the graph anymore. Second call of `begin()` on the same
graph, should not change the graph.

<h3 id="end"><code>end</code></h3>

``` python
end(session)
```

Called at the end of session.

The `session` argument can be used in case the hook wants to run final ops,
such as saving a last checkpoint.

If `session.run()` raises exception other than OutOfRangeError or
StopIteration then `end()` is not called.
Note the difference between `end()` and `after_run()` behavior when
`session.run()` raises OutOfRangeError or StopIteration. In that case
`end()` is called but `after_run()` is not called.

#### Args:

* <b>`session`</b>: A TensorFlow Session that will be soon closed.



