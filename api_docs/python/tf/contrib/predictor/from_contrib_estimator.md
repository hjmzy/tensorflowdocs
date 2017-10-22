<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.predictor.from_contrib_estimator" />
</div>

# tf.contrib.predictor.from_contrib_estimator

``` python
from_contrib_estimator(
    estimator,
    prediction_input_fn,
    input_alternative_key=None,
    output_alternative_key=None,
    graph=None
)
```



Defined in [`tensorflow/contrib/predictor/predictor_factories.py`](https://www.tensorflow.org/code/tensorflow/contrib/predictor/predictor_factories.py).

Constructs a `Predictor` from a `tf.contrib.learn.Estimator`.

#### Args:

* <b>`estimator`</b>: an instance of `tf.contrib.learn.Estimator`.
* <b>`prediction_input_fn`</b>: a function that takes no arguments and returns an
    instance of `InputFnOps`.
* <b>`input_alternative_key`</b>: Optional. Specify the input alternative used for
    prediction.
* <b>`output_alternative_key`</b>: Specify the output alternative used for
    prediction. Not needed for single-headed models but required for
    multi-headed models.
* <b>`graph`</b>: Optional. The Tensorflow `graph` in which prediction should be
    done.


#### Returns:

An initialized `Predictor`.


#### Raises:

* <b>`TypeError`</b>: if `estimator` is a core `Estimator` instead of a contrib
    `Estimator`.