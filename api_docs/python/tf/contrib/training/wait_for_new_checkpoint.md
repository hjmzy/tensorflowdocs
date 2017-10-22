<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.training.wait_for_new_checkpoint" />
</div>

# tf.contrib.training.wait_for_new_checkpoint

``` python
wait_for_new_checkpoint(
    checkpoint_dir,
    last_checkpoint=None,
    seconds_to_sleep=1,
    timeout=None
)
```



Defined in [`tensorflow/contrib/training/python/training/evaluation.py`](https://www.tensorflow.org/code/tensorflow/contrib/training/python/training/evaluation.py).

Waits until a new checkpoint file is found.

#### Args:

* <b>`checkpoint_dir`</b>: The directory in which checkpoints are saved.
* <b>`last_checkpoint`</b>: The last checkpoint path used or `None` if we're expecting
    a checkpoint for the first time.
* <b>`seconds_to_sleep`</b>: The number of seconds to sleep for before looking for a
    new checkpoint.
* <b>`timeout`</b>: The maximum amount of time to wait. If left as `None`, then the
    process will wait indefinitely.


#### Returns:

a new checkpoint path, or None if the timeout was reached.