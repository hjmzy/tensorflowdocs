<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.nest.assert_same_structure" />
</div>

# tf.contrib.framework.nest.assert_same_structure

``` python
assert_same_structure(
    nest1,
    nest2,
    check_types=True
)
```



Defined in [`tensorflow/python/util/nest.py`](https://www.tensorflow.org/code/tensorflow/python/util/nest.py).

Asserts that two structures are nested in the same way.

#### Args:

* <b>`nest1`</b>: an arbitrarily nested structure.
* <b>`nest2`</b>: an arbitrarily nested structure.
* <b>`check_types`</b>: if `True` (default) types of sequences are checked as
      well, including the keys of dictionaries. If set to `False`, for example
      a list and a tuple of objects will look the same if they have the same
      size.


#### Raises:

* <b>`ValueError`</b>: If the two structures do not have the same number of elements or
    if the two structures are not nested in the same way.
* <b>`TypeError`</b>: If the two structures differ in the type of sequence in any of
    their substructures. Only possible if `check_types` is `True`.