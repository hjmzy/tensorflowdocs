<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.Saver" />
<meta itemprop="property" content="last_checkpoints"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="as_saver_def"/>
<meta itemprop="property" content="build"/>
<meta itemprop="property" content="export_meta_graph"/>
<meta itemprop="property" content="from_proto"/>
<meta itemprop="property" content="recover_last_checkpoints"/>
<meta itemprop="property" content="restore"/>
<meta itemprop="property" content="save"/>
<meta itemprop="property" content="set_last_checkpoints"/>
<meta itemprop="property" content="set_last_checkpoints_with_time"/>
<meta itemprop="property" content="to_proto"/>
</div>

# tf.train.Saver

## Class `Saver`





Defined in [`tensorflow/python/training/saver.py`](https://www.tensorflow.org/code/tensorflow/python/training/saver.py).

See the guides: [Exporting and Importing a MetaGraph > Exporting a Complete Model to MetaGraph](../../../../api_guides/python/meta_graph.md#Exporting_a_Complete_Model_to_MetaGraph), [Exporting and Importing a MetaGraph](../../../../api_guides/python/meta_graph.md), [Variables > Saving and Restoring Variables](../../../../api_guides/python/state_ops.md#Saving_and_Restoring_Variables)

Saves and restores variables.

See [Variables](../../../../programmers_guide/variables.md)
for an overview of variables, saving and restoring.

The `Saver` class adds ops to save and restore variables to and from
*checkpoints*.  It also provides convenience methods to run these ops.

Checkpoints are binary files in a proprietary format which map variable names
to tensor values.  The best way to examine the contents of a checkpoint is to
load it using a `Saver`.

Savers can automatically number checkpoint filenames with a provided counter.
This lets you keep multiple checkpoints at different steps while training a
model.  For example you can number the checkpoint filenames with the training
step number.  To avoid filling up disks, savers manage checkpoint files
automatically. For example, they can keep only the N most recent files, or
one checkpoint for every N hours of training.

You number checkpoint filenames by passing a value to the optional
`global_step` argument to `save()`:

```python
saver.save(sess, 'my-model', global_step=0) ==> filename: 'my-model-0'
...
saver.save(sess, 'my-model', global_step=1000) ==> filename: 'my-model-1000'
```

Additionally, optional arguments to the `Saver()` constructor let you control
the proliferation of checkpoint files on disk:

* `max_to_keep` indicates the maximum number of recent checkpoint files to
  keep.  As new files are created, older files are deleted.  If None or 0,
  all checkpoint files are kept.  Defaults to 5 (that is, the 5 most recent
  checkpoint files are kept.)

* `keep_checkpoint_every_n_hours`: In addition to keeping the most recent
  `max_to_keep` checkpoint files, you might want to keep one checkpoint file
  for every N hours of training.  This can be useful if you want to later
  analyze how a model progressed during a long training session.  For
  example, passing `keep_checkpoint_every_n_hours=2` ensures that you keep
  one checkpoint file for every 2 hours of training.  The default value of
  10,000 hours effectively disables the feature.

Note that you still have to call the `save()` method to save the model.
Passing these arguments to the constructor will not save variables
automatically for you.

A training program that saves regularly looks like:

```python
...
# Create a saver.
saver = tf.train.Saver(...variables...)
# Launch the graph and train, saving the model every 1,000 steps.
sess = tf.Session()
for step in xrange(1000000):
    sess.run(..training_op..)
    if step % 1000 == 0:
        # Append the step number to the checkpoint name:
        saver.save(sess, 'my-model', global_step=step)
```

In addition to checkpoint files, savers keep a protocol buffer on disk with
the list of recent checkpoints. This is used to manage numbered checkpoint
files and by `latest_checkpoint()`, which makes it easy to discover the path
to the most recent checkpoint. That protocol buffer is stored in a file named
'checkpoint' next to the checkpoint files.

If you create several savers, you can specify a different filename for the
protocol buffer file in the call to `save()`.

## Properties

<h3 id="last_checkpoints"><code>last_checkpoints</code></h3>

List of not-yet-deleted checkpoint filenames.

You can pass any of the returned values to `restore()`.

#### Returns:

A list of checkpoint filenames, sorted from oldest to newest.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    var_list=None,
    reshape=False,
    sharded=False,
    max_to_keep=5,
    keep_checkpoint_every_n_hours=10000.0,
    name=None,
    restore_sequentially=False,
    saver_def=None,
    builder=None,
    defer_build=False,
    allow_empty=False,
    write_version=tf.train.SaverDef.V2,
    pad_step_number=False,
    save_relative_paths=False,
    filename=None
)
```

Creates a `Saver`.

The constructor adds ops to save and restore variables.

`var_list` specifies the variables that will be saved and restored. It can
be passed as a `dict` or a list:

* A `dict` of names to variables: The keys are the names that will be
  used to save or restore the variables in the checkpoint files.
* A list of variables: The variables will be keyed with their op name in
  the checkpoint files.

For example:

```python
v1 = tf.Variable(..., name='v1')
v2 = tf.Variable(..., name='v2')

# Pass the variables as a dict:
saver = tf.train.Saver({'v1': v1, 'v2': v2})

# Or pass them as a list.
saver = tf.train.Saver([v1, v2])
# Passing a list is equivalent to passing a dict with the variable op names
# as keys:
saver = tf.train.Saver({v.op.name: v for v in [v1, v2]})
```

The optional `reshape` argument, if `True`, allows restoring a variable from
a save file where the variable had a different shape, but the same number
of elements and type.  This is useful if you have reshaped a variable and
want to reload it from an older checkpoint.

The optional `sharded` argument, if `True`, instructs the saver to shard
checkpoints per device.

#### Args:

* <b>`var_list`</b>: A list of `Variable`/`SaveableObject`, or a dictionary mapping
    names to `SaveableObject`s. If `None`, defaults to the list of all
    saveable objects.
* <b>`reshape`</b>: If `True`, allows restoring parameters from a checkpoint
    where the variables have a different shape.
* <b>`sharded`</b>: If `True`, shard the checkpoints, one per device.
* <b>`max_to_keep`</b>: Maximum number of recent checkpoints to keep.
    Defaults to 5.
* <b>`keep_checkpoint_every_n_hours`</b>: How often to keep checkpoints.
    Defaults to 10,000 hours.
* <b>`name`</b>: String.  Optional name to use as a prefix when adding operations.
* <b>`restore_sequentially`</b>: A `Bool`, which if true, causes restore of different
    variables to happen sequentially within each device.  This can lower
    memory usage when restoring very large models.
* <b>`saver_def`</b>: Optional `SaverDef` proto to use instead of running the
    builder. This is only useful for specialty code that wants to recreate
    a `Saver` object for a previously built `Graph` that had a `Saver`.
    The `saver_def` proto should be the one returned by the
    `as_saver_def()` call of the `Saver` that was created for that `Graph`.
* <b>`builder`</b>: Optional `SaverBuilder` to use if a `saver_def` was not provided.
    Defaults to `BaseSaverBuilder()`.
* <b>`defer_build`</b>: If `True`, defer adding the save and restore ops to the
    `build()` call. In that case `build()` should be called before
    finalizing the graph or using the saver.
* <b>`allow_empty`</b>: If `False` (default) raise an error if there are no
    variables in the graph. Otherwise, construct the saver anyway and make
    it a no-op.
* <b>`write_version`</b>: controls what format to use when saving checkpoints.  It
    also affects certain filepath matching logic.  The V2 format is the
    recommended choice: it is much more optimized than V1 in terms of
    memory required and latency incurred during restore.  Regardless of
    this flag, the Saver is able to restore from both V2 and V1 checkpoints.
* <b>`pad_step_number`</b>: if True, pads the global step number in the checkpoint
    filepaths to some fixed width (8 by default).  This is turned off by
    default.
* <b>`save_relative_paths`</b>: If `True`, will write relative paths to the
    checkpoint state file. This is needed if the user wants to copy the
    checkpoint directory and reload from the copied directory.
* <b>`filename`</b>: If known at graph construction time, filename used for variable
    loading/saving.


#### Raises:

* <b>`TypeError`</b>: If `var_list` is invalid.
* <b>`ValueError`</b>: If any of the keys or values in `var_list` are not unique.

<h3 id="as_saver_def"><code>as_saver_def</code></h3>

``` python
as_saver_def()
```

Generates a `SaverDef` representation of this saver.

#### Returns:

A `SaverDef` proto.

<h3 id="build"><code>build</code></h3>

``` python
build()
```



<h3 id="export_meta_graph"><code>export_meta_graph</code></h3>

``` python
export_meta_graph(
    filename=None,
    collection_list=None,
    as_text=False,
    export_scope=None,
    clear_devices=False,
    clear_extraneous_savers=False
)
```

Writes `MetaGraphDef` to save_path/filename.

#### Args:

* <b>`filename`</b>: Optional meta_graph filename including the path.
* <b>`collection_list`</b>: List of string keys to collect.
* <b>`as_text`</b>: If `True`, writes the meta_graph as an ASCII proto.
* <b>`export_scope`</b>: Optional `string`. Name scope to remove.
* <b>`clear_devices`</b>: Whether or not to clear the device field for an `Operation`
    or `Tensor` during export.
* <b>`clear_extraneous_savers`</b>: Remove any Saver-related information from the
    graph (both Save/Restore ops and SaverDefs) that are not associated
    with this Saver.


#### Returns:

A `MetaGraphDef` proto.

<h3 id="from_proto"><code>from_proto</code></h3>

``` python
@staticmethod
from_proto(
    saver_def,
    import_scope=None
)
```

Returns a `Saver` object created from `saver_def`.

#### Args:

* <b>`saver_def`</b>: a `SaverDef` protocol buffer.
* <b>`import_scope`</b>: Optional `string`. Name scope to use.


#### Returns:

A `Saver` built from saver_def.

<h3 id="recover_last_checkpoints"><code>recover_last_checkpoints</code></h3>

``` python
recover_last_checkpoints(checkpoint_paths)
```

Recovers the internal saver state after a crash.

This method is useful for recovering the "self._last_checkpoints" state.

Globs for the checkpoints pointed to by `checkpoint_paths`.  If the files
exist, use their mtime as the checkpoint timestamp.

#### Args:

* <b>`checkpoint_paths`</b>: a list of checkpoint paths.

<h3 id="restore"><code>restore</code></h3>

``` python
restore(
    sess,
    save_path
)
```

Restores previously saved variables.

This method runs the ops added by the constructor for restoring variables.
It requires a session in which the graph was launched.  The variables to
restore do not have to have been initialized, as restoring is itself a way
to initialize variables.

The `save_path` argument is typically a value previously returned from a
`save()` call, or a call to `latest_checkpoint()`.

#### Args:

* <b>`sess`</b>: A `Session` to use to restore the parameters. None in eager mode.
* <b>`save_path`</b>: Path where parameters were previously saved.


#### Raises:

* <b>`ValueError`</b>: If save_path is None.

<h3 id="save"><code>save</code></h3>

``` python
save(
    sess,
    save_path,
    global_step=None,
    latest_filename=None,
    meta_graph_suffix='meta',
    write_meta_graph=True,
    write_state=True
)
```

Saves variables.

This method runs the ops added by the constructor for saving variables.
It requires a session in which the graph was launched.  The variables to
save must also have been initialized.

The method returns the path of the newly created checkpoint file.  This
path can be passed directly to a call to `restore()`.

#### Args:

* <b>`sess`</b>: A Session to use to save the variables. None in eager mode.
* <b>`save_path`</b>: String.  Path to the checkpoint filename.  If the saver is
    `sharded`, this is the prefix of the sharded checkpoint filename.
* <b>`global_step`</b>: If provided the global step number is appended to
    `save_path` to create the checkpoint filename. The optional argument
    can be a `Tensor`, a `Tensor` name or an integer.
* <b>`latest_filename`</b>: Optional name for the protocol buffer file that will
    contains the list of most recent checkpoint filenames.  That file,
    kept in the same directory as the checkpoint files, is automatically
    managed by the saver to keep track of recent checkpoints.  Defaults to
    'checkpoint'.
* <b>`meta_graph_suffix`</b>: Suffix for `MetaGraphDef` file. Defaults to 'meta'.
* <b>`write_meta_graph`</b>: `Boolean` indicating whether or not to write the meta
    graph file.
* <b>`write_state`</b>: `Boolean` indicating whether or not to write the
    `CheckpointStateProto`.


#### Returns:

A string: path at which the variables were saved.  If the saver is
  sharded, this string ends with: '-?????-of-nnnnn' where 'nnnnn'
  is the number of shards created.
If the saver is empty, returns None.


#### Raises:

* <b>`TypeError`</b>: If `sess` is not a `Session`.
* <b>`ValueError`</b>: If `latest_filename` contains path components, or if it
    collides with `save_path`.
* <b>`RuntimeError`</b>: If save and restore ops weren't built.

<h3 id="set_last_checkpoints"><code>set_last_checkpoints</code></h3>

``` python
set_last_checkpoints(last_checkpoints)
```

DEPRECATED: Use set_last_checkpoints_with_time.

Sets the list of old checkpoint filenames.

#### Args:

* <b>`last_checkpoints`</b>: A list of checkpoint filenames.


#### Raises:

* <b>`AssertionError`</b>: If last_checkpoints is not a list.

<h3 id="set_last_checkpoints_with_time"><code>set_last_checkpoints_with_time</code></h3>

``` python
set_last_checkpoints_with_time(last_checkpoints_with_time)
```

Sets the list of old checkpoint filenames and timestamps.

#### Args:

* <b>`last_checkpoints_with_time`</b>: A list of tuples of checkpoint filenames and
    timestamps.


#### Raises:

* <b>`AssertionError`</b>: If last_checkpoints_with_time is not a list.

<h3 id="to_proto"><code>to_proto</code></h3>

``` python
to_proto(export_scope=None)
```

Converts this `Saver` to a `SaverDef` protocol buffer.

#### Args:

* <b>`export_scope`</b>: Optional `string`. Name scope to remove.


#### Returns:

A `SaverDef` protocol buffer.



