<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.SecondOrStepTimer" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="last_triggered_step"/>
<meta itemprop="property" content="reset"/>
<meta itemprop="property" content="should_trigger_for_step"/>
<meta itemprop="property" content="update_last_triggered_step"/>
</div>

# tf.train.SecondOrStepTimer

## Class `SecondOrStepTimer`





Defined in [`tensorflow/python/training/basic_session_run_hooks.py`](https://www.tensorflow.org/code/tensorflow/python/training/basic_session_run_hooks.py).

Timer that triggers at most once every N seconds or once every N steps.
  

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    every_secs=None,
    every_steps=None
)
```



<h3 id="last_triggered_step"><code>last_triggered_step</code></h3>

``` python
last_triggered_step()
```



<h3 id="reset"><code>reset</code></h3>

``` python
reset()
```



<h3 id="should_trigger_for_step"><code>should_trigger_for_step</code></h3>

``` python
should_trigger_for_step(step)
```

Return true if the timer should trigger for the specified step.

#### Args:

* <b>`step`</b>: Training step to trigger on.


#### Returns:

True if the difference between the current time and the time of the last
trigger exceeds `every_secs`, or if the difference between the current
step and the last triggered step exceeds `every_steps`. False otherwise.

<h3 id="update_last_triggered_step"><code>update_last_triggered_step</code></h3>

``` python
update_last_triggered_step(step)
```





