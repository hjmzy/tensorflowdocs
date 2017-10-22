<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.learn.NotFittedError" />
</div>

# tf.contrib.learn.NotFittedError

## Class `NotFittedError`





Defined in [`tensorflow/contrib/learn/python/learn/estimators/_sklearn.py`](https://www.tensorflow.org/code/tensorflow/contrib/learn/python/learn/estimators/_sklearn.py).

Exception class to raise if estimator is used before fitting.

This class inherits from both ValueError and AttributeError to help with
exception handling and backward compatibility.

Examples:
>>> from sklearn.svm import LinearSVC
>>> from sklearn.exceptions import NotFittedError
>>> try:
...     LinearSVC().predict([[1, 2], [2, 3], [3, 4]])
... except NotFittedError as e:
...     print(repr(e))
...                        # doctest: +NORMALIZE_WHITESPACE +ELLIPSIS
NotFittedError('This LinearSVC instance is not fitted yet',)

Copied from
https://github.com/scikit-learn/scikit-learn/master/sklearn/exceptions.py

