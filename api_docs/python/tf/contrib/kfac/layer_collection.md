<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.layer_collection" />
<meta itemprop="property" content="APPROX_DIAGONAL_NAME"/>
<meta itemprop="property" content="APPROX_FULL_NAME"/>
<meta itemprop="property" content="APPROX_KRONECKER_NAME"/>
</div>

# Module: tf.contrib.kfac.layer_collection



Defined in [`tensorflow/contrib/kfac/python/ops/layer_collection_lib.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/layer_collection_lib.py).

Registry for layers and their parameters/variables.

This represents the collection of all layers in the approximate Fisher
information matrix to which a particular FisherBlock may belong. That is, we
might have several layer collections for one TF graph (if we have multiple K-FAC
optimizers being used, for example.)

## Classes

[`class LayerCollection`](../../../tf/contrib/kfac/layer_collection/LayerCollection.md): Registry of information about layers and losses.

[`class LayerParametersDict`](../../../tf/contrib/kfac/layer_collection/LayerParametersDict.md): An OrderedDict where keys are Tensors or tuples of Tensors.

## Other Members

`APPROX_DIAGONAL_NAME`

`APPROX_FULL_NAME`

`APPROX_KRONECKER_NAME`

