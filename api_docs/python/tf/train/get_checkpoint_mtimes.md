<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.get_checkpoint_mtimes" />
</div>

# tf.train.get_checkpoint_mtimes

``` python
get_checkpoint_mtimes(checkpoint_prefixes)
```



Defined in [`tensorflow/python/training/saver.py`](https://www.tensorflow.org/code/tensorflow/python/training/saver.py).

Returns the mtimes (modification timestamps) of the checkpoints.

Globs for the checkpoints pointed to by `checkpoint_prefixes`.  If the files
exist, collect their mtime.  Both V2 and V1 checkpoints are considered, in
that priority.

This is the recommended way to get the mtimes, since it takes into account
the naming difference between V1 and V2 formats.

#### Args:

* <b>`checkpoint_prefixes`</b>: a list of checkpoint paths, typically the results of
    `Saver.save()` or those of `tf.train.latest_checkpoint()`, regardless of
    sharded/non-sharded or V1/V2.

#### Returns:

A list of mtimes (in microseconds) of the found checkpoints.