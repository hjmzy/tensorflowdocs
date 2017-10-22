<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.saved_model.loader" />
</div>

# Module: tf.saved_model.loader



Defined in [`tensorflow/python/saved_model/loader.py`](https://www.tensorflow.org/code/tensorflow/python/saved_model/loader.py).

Loader functionality for SavedModel with hermetic, language-neutral exports.

Load and restore capability for a SavedModel, which may include multiple meta
graph defs. Each SavedModel is associated with a single checkpoint. Each meta
graph def is saved with one or more tags, which are used to identify the exact
meta graph def to load.

The `load` operation requires the session in which to restore the graph
definition and variables, the tags used to identify the meta graph def to
load and the location of the SavedModel.

Upon a load, the subset of variables and assets supplied as part of the specific
meta graph def, will be restored into the supplied session. The values of the
variables though will correspond to the saved values from the first meta graph
added to the SavedModel using `add_meta_graph_and_variables(...)` in
`builder.py`.

Typical usage:

```python
...
builder = tf.saved_model.builder.SavedModelBuilder(export_dir)

with tf.Session(graph=tf.Graph()) as sess:
  ...
  builder.add_meta_graph_and_variables(sess,
                                       ["foo-tag"],
                                       signature_def_map=foo_signatures,
                                       assets_collection=foo_assets)
...

with tf.Session(graph=tf.Graph()) as sess:
  ...
  builder.add_meta_graph(["bar-tag", "baz-tag"],
                         assets_collection=bar_baz_assets)
...

builder.save()

...
with tf.Session(graph=tf.Graph()) as sess:
  tf.saved_model.loader.load(sess, ["foo-tag"], export_dir)
  ...

```

## Functions

[`load(...)`](../../tf/saved_model/loader/load.md): Loads the model from a SavedModel as specified by tags.

[`maybe_saved_model_directory(...)`](../../tf/saved_model/loader/maybe_saved_model_directory.md): Checks whether the provided export directory could contain a SavedModel.

