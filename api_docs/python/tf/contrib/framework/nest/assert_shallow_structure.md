<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.nest.assert_shallow_structure" />
</div>

# tf.contrib.framework.nest.assert_shallow_structure

``` python
assert_shallow_structure(
    shallow_tree,
    input_tree,
    check_types=True
)
```



Defined in [`tensorflow/python/util/nest.py`](https://www.tensorflow.org/code/tensorflow/python/util/nest.py).

Asserts that `shallow_tree` is a shallow structure of `input_tree`.

That is, this function tests if the `input_tree` structure can be created from
the `shallow_tree` structure by replacing its leaf nodes with deeper
tree structures.

Examples:

The following code will raise an exception:
```python
  shallow_tree = ["a", "b"]
  input_tree = ["c", ["d", "e"], "f"]
  assert_shallow_structure(shallow_tree, input_tree)
```

The following code will not raise an exception:
```python
  shallow_tree = ["a", "b"]
  input_tree = ["c", ["d", "e"]]
  assert_shallow_structure(shallow_tree, input_tree)
```

#### Args:

* <b>`shallow_tree`</b>: an arbitrarily nested structure.
* <b>`input_tree`</b>: an arbitrarily nested structure.
* <b>`check_types`</b>: if `True` (default) the sequence types of `shallow_tree` and
    `input_tree` have to be the same.


#### Raises:

* <b>`TypeError`</b>: If `shallow_tree` is a sequence but `input_tree` is not.
* <b>`TypeError`</b>: If the sequence types of `shallow_tree` are different from
    `input_tree`. Only raised if `check_types` is `True`.
* <b>`ValueError`</b>: If the sequence lengths of `shallow_tree` are different from
    `input_tree`.