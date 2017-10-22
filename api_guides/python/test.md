<!-- DO NOT EDIT! Automatically generated file. -->
# Testing
[TOC]

<h2 id="Unit_tests">Unit tests</h2>

TensorFlow provides a convenience class inheriting from `unittest.TestCase`
which adds methods relevant to TensorFlow tests.  Here is an example:

```python
    import tensorflow as tf


    class SquareTest(tf.test.TestCase):

      def testSquare(self):
        with self.test_session():
          x = tf.square([2, 3])
          self.assertAllEqual(x.eval(), [4, 9])


    if __name__ == '__main__':
      tf.test.main()
```

`tf.test.TestCase` inherits from `unittest.TestCase` but adds a few additional
methods.  See [`tf.test.TestCase`](../../api_docs/python/tf/test/TestCase.md) for details.

*   [`tf.test.main`](../../api_docs/python/tf/test/main.md)
*   [`tf.test.TestCase`](../../api_docs/python/tf/test/TestCase.md)
*   [`tf.test.test_src_dir_path`](../../api_docs/python/tf/test/test_src_dir_path.md)

<h2 id="Utilities">Utilities</h2>

Note: `tf.test.mock` is an alias to the python `mock` or `unittest.mock`
depending on the python version.

*   [`tf.test.assert_equal_graph_def`](../../api_docs/python/tf/test/assert_equal_graph_def.md)
*   [`tf.test.get_temp_dir`](../../api_docs/python/tf/test/get_temp_dir.md)
*   [`tf.test.is_built_with_cuda`](../../api_docs/python/tf/test/is_built_with_cuda.md)
*   [`tf.test.is_gpu_available`](../../api_docs/python/tf/test/is_gpu_available.md)
*   [`tf.test.gpu_device_name`](../../api_docs/python/tf/test/gpu_device_name.md)

<h2 id="Gradient_checking">Gradient checking</h2>

[`tf.test.compute_gradient`](../../api_docs/python/tf/test/compute_gradient.md) and [`tf.test.compute_gradient_error`](../../api_docs/python/tf/test/compute_gradient_error.md) perform
numerical differentiation of graphs for comparison against registered analytic
gradients.
