<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.LooperThread" />
<meta itemprop="property" content="daemon"/>
<meta itemprop="property" content="ident"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="getName"/>
<meta itemprop="property" content="isAlive"/>
<meta itemprop="property" content="isDaemon"/>
<meta itemprop="property" content="is_alive"/>
<meta itemprop="property" content="join"/>
<meta itemprop="property" content="loop"/>
<meta itemprop="property" content="run"/>
<meta itemprop="property" content="run_loop"/>
<meta itemprop="property" content="setDaemon"/>
<meta itemprop="property" content="setName"/>
<meta itemprop="property" content="start"/>
<meta itemprop="property" content="start_loop"/>
<meta itemprop="property" content="stop_loop"/>
</div>

# tf.train.LooperThread

## Class `LooperThread`





Defined in [`tensorflow/python/training/coordinator.py`](https://www.tensorflow.org/code/tensorflow/python/training/coordinator.py).

See the guide: [Training > Coordinator and QueueRunner](../../../../api_guides/python/train.md#Coordinator_and_QueueRunner)

A thread that runs code repeatedly, optionally on a timer.

This thread class is intended to be used with a `Coordinator`.  It repeatedly
runs code specified either as `target` and `args` or by the `run_loop()`
method.

Before each run the thread checks if the coordinator has requested stop.  In
that case the looper thread terminates immediately.

If the code being run raises an exception, that exception is reported to the
coordinator and the thread terminates.  The coordinator will then request all
the other threads it coordinates to stop.

You typically pass looper threads to the supervisor `Join()` method.

## Properties

<h3 id="daemon"><code>daemon</code></h3>

A boolean value indicating whether this thread is a daemon thread (True) or not (False).

This must be set before start() is called, otherwise RuntimeError is
raised. Its initial value is inherited from the creating thread; the
main thread is not a daemon thread and therefore all threads created in
the main thread default to daemon = False.

The entire Python program exits when no alive non-daemon threads are
left.

<h3 id="ident"><code>ident</code></h3>

Thread identifier of this thread or None if it has not been started.

This is a nonzero integer. See the thread.get_ident() function. Thread
identifiers may be recycled when a thread exits and another thread is
created. The identifier is available even after the thread has exited.

<h3 id="name"><code>name</code></h3>

A string used for identification purposes only.

It has no semantics. Multiple threads may be given the same name. The
initial name is set by the constructor.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    coord,
    timer_interval_secs,
    target=None,
    args=None,
    kwargs=None
)
```

Create a LooperThread.

#### Args:

* <b>`coord`</b>: A Coordinator.
* <b>`timer_interval_secs`</b>: Time boundaries at which to call Run(), or None
    if it should be called back to back.
* <b>`target`</b>: Optional callable object that will be executed in the thread.
* <b>`args`</b>: Optional arguments to pass to `target` when calling it.
* <b>`kwargs`</b>: Optional keyword arguments to pass to `target` when calling it.


#### Raises:

* <b>`ValueError`</b>: If one of the arguments is invalid.

<h3 id="getName"><code>getName</code></h3>

``` python
getName()
```



<h3 id="isAlive"><code>isAlive</code></h3>

``` python
isAlive()
```

Return whether the thread is alive.

This method returns True just before the run() method starts until just
after the run() method terminates. The module function enumerate()
returns a list of all alive threads.

<h3 id="isDaemon"><code>isDaemon</code></h3>

``` python
isDaemon()
```



<h3 id="is_alive"><code>is_alive</code></h3>

``` python
is_alive()
```

Return whether the thread is alive.

This method returns True just before the run() method starts until just
after the run() method terminates. The module function enumerate()
returns a list of all alive threads.

<h3 id="join"><code>join</code></h3>

``` python
join(timeout=None)
```

Wait until the thread terminates.

This blocks the calling thread until the thread whose join() method is
called terminates -- either normally or through an unhandled exception
or until the optional timeout occurs.

When the timeout argument is present and not None, it should be a
floating point number specifying a timeout for the operation in seconds
(or fractions thereof). As join() always returns None, you must call
isAlive() after join() to decide whether a timeout happened -- if the
thread is still alive, the join() call timed out.

When the timeout argument is not present or None, the operation will
block until the thread terminates.

A thread can be join()ed many times.

join() raises a RuntimeError if an attempt is made to join the current
thread as that would cause a deadlock. It is also an error to join() a
thread before it has been started and attempts to do so raises the same
exception.

<h3 id="loop"><code>loop</code></h3>

``` python
@staticmethod
loop(
    coord,
    timer_interval_secs,
    target,
    args=None,
    kwargs=None
)
```

Start a LooperThread that calls a function periodically.

If `timer_interval_secs` is None the thread calls `target(args)`
repeatedly.  Otherwise `target(args)` is called every `timer_interval_secs`
seconds.  The thread terminates when a stop of the coordinator is
requested.

#### Args:

* <b>`coord`</b>: A Coordinator.
* <b>`timer_interval_secs`</b>: Number. Time boundaries at which to call `target`.
* <b>`target`</b>: A callable object.
* <b>`args`</b>: Optional arguments to pass to `target` when calling it.
* <b>`kwargs`</b>: Optional keyword arguments to pass to `target` when calling it.


#### Returns:

The started thread.

<h3 id="run"><code>run</code></h3>

``` python
run()
```



<h3 id="run_loop"><code>run_loop</code></h3>

``` python
run_loop()
```

Called at 'timer_interval_secs' boundaries.

<h3 id="setDaemon"><code>setDaemon</code></h3>

``` python
setDaemon(daemonic)
```



<h3 id="setName"><code>setName</code></h3>

``` python
setName(name)
```



<h3 id="start"><code>start</code></h3>

``` python
start()
```

Start the thread's activity.

It must be called at most once per thread object. It arranges for the
object's run() method to be invoked in a separate thread of control.

This method will raise a RuntimeError if called more than once on the
same thread object.

<h3 id="start_loop"><code>start_loop</code></h3>

``` python
start_loop()
```

Called when the thread starts.

<h3 id="stop_loop"><code>stop_loop</code></h3>

``` python
stop_loop()
```

Called when the thread stops.



