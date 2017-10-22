<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.lookup.IdTableWithHashBuckets" />
<meta itemprop="property" content="init"/>
<meta itemprop="property" content="key_dtype"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="value_dtype"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="lookup"/>
<meta itemprop="property" content="size"/>
</div>

# tf.contrib.lookup.IdTableWithHashBuckets

## Class `IdTableWithHashBuckets`

Inherits From: [`LookupInterface`](../../../tf/contrib/lookup/LookupInterface.md)



Defined in [`tensorflow/python/ops/lookup_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/lookup_ops.py).

String to Id table wrapper that assigns out-of-vocabulary keys to buckets.

For example, if an instance of `IdTableWithHashBuckets` is initialized with a
string-to-id table that maps:
- emerson -> 0
- lake -> 1
- palmer -> 2

The `IdTableWithHashBuckets` object will performs the following mapping:
- emerson -> 0
- lake -> 1
- palmer -> 2
- <other term> -> bucket id between 3 and 3 + num_oov_buckets - 1, calculated
  by: hash(<term>) % num_oov_buckets + vocab_size

If input_tensor is ["emerson", "lake", "palmer", "king", "crimson"],
the lookup result is [0, 1, 2, 4, 7]

If `table` is None, only out-of-vocabulary buckets are used.

Example usage:

```python
num_oov_buckets = 3
input_tensor = tf.constant(["emerson", "lake", "palmer", "king", "crimnson"])
table = tf.IdTableWithHashBuckets(
    tf.HashTable(tf.TextFileIdTableInitializer(filename), default_value),
    num_oov_buckets)
out = table.lookup(input_tensor).
table.init.run()
print(out.eval())
```

The hash function used for generating out-of-vocabulary buckets ID is handled
by `hasher_spec`.

## Properties

<h3 id="init"><code>init</code></h3>

The table initialization op.

<h3 id="key_dtype"><code>key_dtype</code></h3>

The table key dtype.

<h3 id="name"><code>name</code></h3>

The name of the table.

<h3 id="value_dtype"><code>value_dtype</code></h3>

The table value dtype.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    table,
    num_oov_buckets,
    hasher_spec=tf.contrib.lookup.FastHashSpec,
    name=None,
    key_dtype=None
)
```

Construct a `IdTableWithHashBuckets` object.

#### Args:

* <b>`table`</b>: Table that maps `tf.string` or `tf.int64` keys to `tf.int64` ids.
* <b>`num_oov_buckets`</b>: Number of buckets to use for out-of-vocabulary keys.
* <b>`hasher_spec`</b>: A `HasherSpec` to specify the hash function to use for
    assignation of out-of-vocabulary buckets  (optional).
* <b>`name`</b>: A name for the operation (optional).
* <b>`key_dtype`</b>: Data type of keys passed to `lookup`. Defaults to
    `table.key_dtype` if `table` is specified, otherwise `tf.string`.
    Must be string or integer, and must be castable to `table.key_dtype`.


#### Raises:

* <b>`ValueError`</b>: when `table` in None and `num_oov_buckets` is not positive.
* <b>`TypeError`</b>: when `hasher_spec` is invalid.

<h3 id="lookup"><code>lookup</code></h3>

``` python
lookup(
    keys,
    name=None
)
```

Looks up `keys` in the table, outputs the corresponding values.

It assigns out-of-vocabulary keys to buckets based in their hashes.

#### Args:

* <b>`keys`</b>: Keys to look up. May be either a `SparseTensor` or dense `Tensor`.
* <b>`name`</b>: Optional name for the op.


#### Returns:

A `SparseTensor` if keys are sparse, otherwise a dense `Tensor`.


#### Raises:

* <b>`TypeError`</b>: when `keys` doesn't match the table key data type.

<h3 id="size"><code>size</code></h3>

``` python
size(name=None)
```

Compute the number of elements in this table.



