<!-- DO NOT EDIT! Automatically generated file. -->
# Linear Algebra (contrib)
[TOC]

Linear algebra libraries for TensorFlow.

<h2 id="_LinearOperator_">`LinearOperator`</h2>

Subclasses of `LinearOperator` provide a access to common methods on a
(batch) matrix, without the need to materialize the matrix.  This allows:

* Matrix free computations
* Different operators to take advantage of special structure, while providing a
  consistent API to users.

### Base class

*   [`tf.contrib.linalg.LinearOperator`](../../api_docs/python/tf/linalg/LinearOperator.md)

### Individual operators

*   [`tf.contrib.linalg.LinearOperatorDiag`](../../api_docs/python/tf/linalg/LinearOperatorDiag.md)
*   [`tf.contrib.linalg.LinearOperatorIdentity`](../../api_docs/python/tf/linalg/LinearOperatorIdentity.md)
*   [`tf.contrib.linalg.LinearOperatorScaledIdentity`](../../api_docs/python/tf/linalg/LinearOperatorScaledIdentity.md)
*   [`tf.contrib.linalg.LinearOperatorFullMatrix`](../../api_docs/python/tf/linalg/LinearOperatorFullMatrix.md)
*   [`tf.contrib.linalg.LinearOperatorLowerTriangular`](../../api_docs/python/tf/linalg/LinearOperatorLowerTriangular.md)
*   [`tf.contrib.linalg.LinearOperatorLowRankUpdate`](../../api_docs/python/tf/linalg/LinearOperatorLowRankUpdate.md)

### Transformations and Combinations of operators

*   [`tf.contrib.linalg.LinearOperatorComposition`](../../api_docs/python/tf/linalg/LinearOperatorComposition.md)
