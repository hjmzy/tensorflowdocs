<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.export.PredictOutput" />
<meta itemprop="property" content="outputs"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="as_signature_def"/>
</div>

# tf.estimator.export.PredictOutput

## Class `PredictOutput`

Inherits From: [`ExportOutput`](../../../tf/estimator/export/ExportOutput.md)



Defined in [`tensorflow/python/estimator/export/export_output.py`](https://www.tensorflow.org/code/tensorflow/python/estimator/export/export_output.py).

Represents the output of a generic prediction head.

A generic prediction need not be either a classification or a regression.

Named outputs must be provided as a dict from string to `Tensor`,

## Properties

<h3 id="outputs"><code>outputs</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(outputs)
```

Constructor for PredictOutput.

#### Args:

* <b>`outputs`</b>: A `Tensor` or a dict of string to `Tensor` representing the
    predictions.


#### Raises:

* <b>`ValueError`</b>: if the outputs is not dict, or any of its keys are not
      strings, or any of its values are not `Tensor`s.

<h3 id="as_signature_def"><code>as_signature_def</code></h3>

``` python
as_signature_def(receiver_tensors)
```





