<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.export.ExportOutput" />
<meta itemprop="property" content="as_signature_def"/>
</div>

# tf.estimator.export.ExportOutput

## Class `ExportOutput`





Defined in [`tensorflow/python/estimator/export/export_output.py`](https://www.tensorflow.org/code/tensorflow/python/estimator/export/export_output.py).

Represents an output of a model that can be served.

These typically correspond to model heads.

## Methods

<h3 id="as_signature_def"><code>as_signature_def</code></h3>

``` python
as_signature_def(receiver_tensors)
```

Generate a SignatureDef proto for inclusion in a MetaGraphDef.

The SignatureDef will specify outputs as described in this ExportOutput,
and will use the provided receiver_tensors as inputs.

#### Args:

* <b>`receiver_tensors`</b>: a `Tensor`, or a dict of string to `Tensor`, specifying
    input nodes that will be fed.



