<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.estimator.dnn_logit_fn_builder" />
</div>

# tf.contrib.estimator.dnn_logit_fn_builder

``` python
dnn_logit_fn_builder(
    units,
    hidden_units,
    feature_columns,
    activation_fn,
    dropout,
    input_layer_partitioner
)
```



Defined in [`tensorflow/python/estimator/canned/dnn.py`](https://www.tensorflow.org/code/tensorflow/python/estimator/canned/dnn.py).

Function builder for a dnn logit_fn.

#### Args:

* <b>`units`</b>: An int indicating the dimension of the logit layer, or a list of ints
    to build multiple logits in the MultiHead case.
* <b>`hidden_units`</b>: Iterable of integer number of hidden units per layer.
* <b>`feature_columns`</b>: Iterable of `feature_column._FeatureColumn` model inputs.
* <b>`activation_fn`</b>: Activation function applied to each layer.
* <b>`dropout`</b>: When not `None`, the probability we will drop out a given
    coordinate.
* <b>`input_layer_partitioner`</b>: Partitioner for input layer.


#### Returns:

A logit_fn (see below).


#### Raises:

* <b>`ValueError`</b>: If units is not an int or a list.