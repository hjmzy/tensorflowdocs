<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.utils.column_to_tensors" />
</div>

# tf.contrib.kfac.utils.column_to_tensors

``` python
column_to_tensors(
    tensors_template,
    colvec
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/utils.py).

Converts a column vector back to the shape of the given template.

#### Args:

* <b>`tensors_template`</b>: A tensor or list of tensors.
* <b>`colvec`</b>: A 2d column vector with the same shape as the value of
      tensors_to_column(tensors_template).


#### Returns:

X, where X is tensor or list of tensors with the properties:
 1) tensors_to_column(X) = colvec
 2) X (or its elements) have the same shape as tensors_template (or its
    elements)