<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.Tensor" />
<meta itemprop="property" content="device"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="op"/>
<meta itemprop="property" content="shape"/>
<meta itemprop="property" content="value_index"/>
<meta itemprop="property" content="__abs__"/>
<meta itemprop="property" content="__add__"/>
<meta itemprop="property" content="__and__"/>
<meta itemprop="property" content="__bool__"/>
<meta itemprop="property" content="__div__"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__floordiv__"/>
<meta itemprop="property" content="__ge__"/>
<meta itemprop="property" content="__getitem__"/>
<meta itemprop="property" content="__gt__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__invert__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="__le__"/>
<meta itemprop="property" content="__lt__"/>
<meta itemprop="property" content="__matmul__"/>
<meta itemprop="property" content="__mod__"/>
<meta itemprop="property" content="__mul__"/>
<meta itemprop="property" content="__neg__"/>
<meta itemprop="property" content="__nonzero__"/>
<meta itemprop="property" content="__or__"/>
<meta itemprop="property" content="__pow__"/>
<meta itemprop="property" content="__radd__"/>
<meta itemprop="property" content="__rand__"/>
<meta itemprop="property" content="__rdiv__"/>
<meta itemprop="property" content="__rfloordiv__"/>
<meta itemprop="property" content="__rmatmul__"/>
<meta itemprop="property" content="__rmod__"/>
<meta itemprop="property" content="__rmul__"/>
<meta itemprop="property" content="__ror__"/>
<meta itemprop="property" content="__rpow__"/>
<meta itemprop="property" content="__rsub__"/>
<meta itemprop="property" content="__rtruediv__"/>
<meta itemprop="property" content="__rxor__"/>
<meta itemprop="property" content="__sub__"/>
<meta itemprop="property" content="__truediv__"/>
<meta itemprop="property" content="__xor__"/>
<meta itemprop="property" content="consumers"/>
<meta itemprop="property" content="eval"/>
<meta itemprop="property" content="get_shape"/>
<meta itemprop="property" content="set_shape"/>
<meta itemprop="property" content="OVERLOADABLE_OPERATORS"/>
<meta itemprop="property" content="__array_priority__"/>
</div>

# tf.Tensor

## Class `Tensor`





Defined in [`tensorflow/python/framework/ops.py`](https://www.tensorflow.org/code/tensorflow/python/framework/ops.py).

See the guide: [Building Graphs > Core graph data structures](../../../api_guides/python/framework.md#Core_graph_data_structures)

Represents one of the outputs of an `Operation`.

A `Tensor` is a symbolic handle to one of the outputs of an
`Operation`. It does not hold the values of that operation's output,
but instead provides a means of computing those values in a
TensorFlow [`tf.Session`](../tf/Session.md).

This class has two primary purposes:

1. A `Tensor` can be passed as an input to another `Operation`.
   This builds a dataflow connection between operations, which
   enables TensorFlow to execute an entire `Graph` that represents a
   large, multi-step computation.

2. After the graph has been launched in a session, the value of the
   `Tensor` can be computed by passing it to
   [`tf.Session.run`](../tf/Session.md#run).
   `t.eval()` is a shortcut for calling
   `tf.get_default_session().run(t)`.

In the following example, `c`, `d`, and `e` are symbolic `Tensor`
objects, whereas `result` is a numpy array that stores a concrete
value:

```python
# Build a dataflow graph.
c = tf.constant([[1.0, 2.0], [3.0, 4.0]])
d = tf.constant([[1.0, 1.0], [0.0, 1.0]])
e = tf.matmul(c, d)

# Construct a `Session` to execute the graph.
sess = tf.Session()

# Execute the graph and store the value that `e` represents in `result`.
result = sess.run(e)
```

## Properties

<h3 id="device"><code>device</code></h3>

The name of the device on which this tensor will be produced, or None.

<h3 id="dtype"><code>dtype</code></h3>

The `DType` of elements in this tensor.

<h3 id="graph"><code>graph</code></h3>

The `Graph` that contains this tensor.

<h3 id="name"><code>name</code></h3>

The string name of this tensor.

<h3 id="op"><code>op</code></h3>

The `Operation` that produces this tensor as an output.

<h3 id="shape"><code>shape</code></h3>

Returns the `TensorShape` that represents the shape of this tensor.

The shape is computed using shape inference functions that are
registered in the Op for each `Operation`.  See
[`tf.TensorShape`](../tf/TensorShape.md)
for more details of what a shape represents.

The inferred shape of a tensor is used to provide shape
information without having to launch the graph in a session. This
can be used for debugging, and providing early error messages. For
example:

```python
c = tf.constant([[1.0, 2.0, 3.0], [4.0, 5.0, 6.0]])

print(c.shape)
==> TensorShape([Dimension(2), Dimension(3)])

d = tf.constant([[1.0, 0.0], [0.0, 1.0], [1.0, 0.0], [0.0, 1.0]])

print(d.shape)
==> TensorShape([Dimension(4), Dimension(2)])

# Raises a ValueError, because `c` and `d` do not have compatible
# inner dimensions.
e = tf.matmul(c, d)

f = tf.matmul(c, d, transpose_a=True, transpose_b=True)

print(f.shape)
==> TensorShape([Dimension(3), Dimension(4)])
```

In some cases, the inferred shape may have unknown dimensions. If
the caller has additional information about the values of these
dimensions, `Tensor.set_shape()` can be used to augment the
inferred shape.

#### Returns:

A `TensorShape` representing the shape of this tensor.

<h3 id="value_index"><code>value_index</code></h3>

The index of this tensor in the outputs of its `Operation`.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    op,
    value_index,
    dtype
)
```

Creates a new `Tensor`.

#### Args:

* <b>`op`</b>: An `Operation`. `Operation` that computes this tensor.
* <b>`value_index`</b>: An `int`. Index of the operation's endpoint that produces
    this tensor.
* <b>`dtype`</b>: A `DType`. Type of elements stored in this tensor.


#### Raises:

* <b>`TypeError`</b>: If the op is not an `Operation`.

<h3 id="__abs__"><code>__abs__</code></h3>

``` python
__abs__(
    x,
    name=None
)
```

Computes the absolute value of a tensor.

Given a tensor `x` of complex numbers, this operation returns a tensor of type
`float32` or `float64` that is the absolute value of each element in `x`. All
elements in `x` must be complex numbers of the form \\(a + bj\\). The
absolute value is computed as \\( \sqrt{a^2 + b^2}\\).  For example:
```python
x = tf.constant([[-2.25 + 4.75j], [-3.25 + 5.75j]])
tf.abs(x)  # [5.25594902, 6.60492229]
```

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor` of type `float32`, `float64`, `int32`,
    `int64`, `complex64` or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` or `SparseTensor` the same size and type as `x` with absolute
  values.
Note, for `complex64` or `complex128' input, the returned `Tensor` will be
  of type `float32` or `float64`, respectively.

<h3 id="__add__"><code>__add__</code></h3>

``` python
__add__(
    x,
    y
)
```

Returns x + y element-wise.

*NOTE*: `Add` supports broadcasting. `AddN` does not. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `half`, `float32`, `float64`, `uint8`, `int8`, `int16`, `int32`, `int64`, `complex64`, `complex128`, `string`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

<h3 id="__and__"><code>__and__</code></h3>

``` python
__and__(
    x,
    y
)
```

Returns the truth value of x AND y element-wise.

*NOTE*: `LogicalAnd` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`y`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

<h3 id="__bool__"><code>__bool__</code></h3>

``` python
__bool__()
```

Dummy method to prevent a tensor from being used as a Python `bool`.

This overload raises a `TypeError` when the user inadvertently
treats a `Tensor` as a boolean (e.g. in an `if` statement). For
example:

```python
if tf.constant(True):  # Will raise.
  # ...

if tf.constant(5) < tf.constant(7):  # Will raise.
  # ...
```

This disallows ambiguities between testing the Python value vs testing the
dynamic condition of the `Tensor`.

#### Raises:

`TypeError`.

<h3 id="__div__"><code>__div__</code></h3>

``` python
__div__(
    x,
    y
)
```

Divide two values using Python 2 semantics. Used for Tensor.__div__.

#### Args:

* <b>`x`</b>: `Tensor` numerator of real numeric type.
* <b>`y`</b>: `Tensor` denominator of real numeric type.
* <b>`name`</b>: A name for the operation (optional).

#### Returns:

`x / y` returns the quotient of x and y.

<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```



<h3 id="__floordiv__"><code>__floordiv__</code></h3>

``` python
__floordiv__(
    x,
    y
)
```

Divides `x / y` elementwise, rounding toward the most negative integer.

The same as `tf.div(x,y)` for integers, but uses `tf.floor(tf.div(x,y))` for
floating point arguments so that the result is always an integer (though
possibly an integer represented as floating point).  This op is generated by
`x // y` floor division in Python 3 and in Python 2.7 with
`from __future__ import division`.

Note that for efficiency, `floordiv` uses C semantics for negative numbers
(unlike Python and Numpy).

`x` and `y` must have the same type, and the result will have the same type
as well.

#### Args:

* <b>`x`</b>: `Tensor` numerator of real numeric type.
* <b>`y`</b>: `Tensor` denominator of real numeric type.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

`x / y` rounded down (except possibly towards zero for negative integers).


#### Raises:

* <b>`TypeError`</b>: If the inputs are complex.

<h3 id="__ge__"><code>__ge__</code></h3>

``` python
__ge__(
    x,
    y,
    name=None
)
```

Returns the truth value of (x >= y) element-wise.

*NOTE*: `GreaterEqual` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `int64`, `uint8`, `int16`, `int8`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

<h3 id="__getitem__"><code>__getitem__</code></h3>

``` python
__getitem__(
    tensor,
    slice_spec,
    var=None
)
```

Overload for Tensor.__getitem__.

This operation extracts the specified region from the tensor.
The notation is similar to NumPy with the restriction that
currently only support basic indexing. That means that
using a tensor as input is not currently allowed

Some useful examples:

```python
# strip leading and trailing 2 elements
foo = tf.constant([1,2,3,4,5,6])
print(foo[2:-2].eval())  # [3,4]

# skip every row and reverse every column
foo = tf.constant([[1,2,3], [4,5,6], [7,8,9]])
print(foo[::2,::-1].eval())  # [[3,2,1], [9,8,7]]

# Insert another dimension
foo = tf.constant([[1,2,3], [4,5,6], [7,8,9]])
print(foo[tf.newaxis, :, :].eval()) # => [[[1,2,3], [4,5,6], [7,8,9]]]
print(foo[:, tf.newaxis, :].eval()) # => [[[1,2,3]], [[4,5,6]], [[7,8,9]]]
print(foo[:, :, tf.newaxis].eval()) # => [[[1],[2],[3]], [[4],[5],[6]],
[[7],[8],[9]]]

# Ellipses (3 equivalent operations)
foo = tf.constant([[1,2,3], [4,5,6], [7,8,9]])
print(foo[tf.newaxis, :, :].eval())  # [[[1,2,3], [4,5,6], [7,8,9]]]
print(foo[tf.newaxis, ...].eval())  # [[[1,2,3], [4,5,6], [7,8,9]]]
print(foo[tf.newaxis].eval())  # [[[1,2,3], [4,5,6], [7,8,9]]]
```

Notes:
  - `tf.newaxis` is `None` as in NumPy.
  - An implicit ellipsis is placed at the end of the `slice_spec`
  - NumPy advanced indexing is currently not supported.

#### Args:

* <b>`tensor`</b>: An ops.Tensor object.
* <b>`slice_spec`</b>: The arguments to Tensor.__getitem__.
* <b>`var`</b>: In the case of variable slice assignment, the Variable
    object to slice (i.e. tensor is the read-only view of this
    variable).


#### Returns:

The appropriate slice of "tensor", based on "slice_spec".


#### Raises:

* <b>`ValueError`</b>: If a slice range is negative size.
* <b>`TypeError`</b>: If the slice indices aren't int, slice, or Ellipsis.

<h3 id="__gt__"><code>__gt__</code></h3>

``` python
__gt__(
    x,
    y,
    name=None
)
```

Returns the truth value of (x > y) element-wise.

*NOTE*: `Greater` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `int64`, `uint8`, `int16`, `int8`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

<h3 id="__invert__"><code>__invert__</code></h3>

``` python
__invert__(
    x,
    name=None
)
```

Returns the truth value of NOT x element-wise.

#### Args:

* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

<h3 id="__iter__"><code>__iter__</code></h3>

``` python
__iter__()
```

Dummy method to prevent iteration. Do not call.

NOTE(mrry): If we register __getitem__ as an overloaded operator,
Python will valiantly attempt to iterate over the Tensor from 0 to
infinity.  Declaring this method prevents this unintended
behavior.

#### Raises:

* <b>`TypeError`</b>: when invoked.

<h3 id="__le__"><code>__le__</code></h3>

``` python
__le__(
    x,
    y,
    name=None
)
```

Returns the truth value of (x <= y) element-wise.

*NOTE*: `LessEqual` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `int64`, `uint8`, `int16`, `int8`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

<h3 id="__lt__"><code>__lt__</code></h3>

``` python
__lt__(
    x,
    y,
    name=None
)
```

Returns the truth value of (x < y) element-wise.

*NOTE*: `Less` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`, `int32`, `int64`, `uint8`, `int16`, `int8`, `uint16`, `half`, `uint32`, `uint64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

<h3 id="__matmul__"><code>__matmul__</code></h3>

``` python
__matmul__(
    x,
    y
)
```

Multiplies matrix `a` by matrix `b`, producing `a` * `b`.

The inputs must, following any transpositions, be tensors of rank >= 2
where the inner 2 dimensions specify valid matrix multiplication arguments,
and any further outer dimensions match.

Both matrices must be of the same type. The supported types are:
`float16`, `float32`, `float64`, `int32`, `complex64`, `complex128`.

Either matrix can be transposed or adjointed (conjugated and transposed) on
the fly by setting one of the corresponding flag to `True`. These are `False`
by default.

If one or both of the matrices contain a lot of zeros, a more efficient
multiplication algorithm can be used by setting the corresponding
`a_is_sparse` or `b_is_sparse` flag to `True`. These are `False` by default.
This optimization is only available for plain matrices (rank-2 tensors) with
datatypes `bfloat16` or `float32`.

For example:

```python
# 2-D tensor `a`
# [[1, 2, 3],
#  [4, 5, 6]]
a = tf.constant([1, 2, 3, 4, 5, 6], shape=[2, 3])

# 2-D tensor `b`
# [[ 7,  8],
#  [ 9, 10],
#  [11, 12]]
b = tf.constant([7, 8, 9, 10, 11, 12], shape=[3, 2])

# `a` * `b`
# [[ 58,  64],
#  [139, 154]]
c = tf.matmul(a, b)


# 3-D tensor `a`
# [[[ 1,  2,  3],
#   [ 4,  5,  6]],
#  [[ 7,  8,  9],
#   [10, 11, 12]]]
a = tf.constant(np.arange(1, 13, dtype=np.int32),
                shape=[2, 2, 3])

# 3-D tensor `b`
# [[[13, 14],
#   [15, 16],
#   [17, 18]],
#  [[19, 20],
#   [21, 22],
#   [23, 24]]]
b = tf.constant(np.arange(13, 25, dtype=np.int32),
                shape=[2, 3, 2])

# `a` * `b`
# [[[ 94, 100],
#   [229, 244]],
#  [[508, 532],
#   [697, 730]]]
c = tf.matmul(a, b)

# Since python >= 3.5 the @ operator is supported (see PEP 465).
# In TensorFlow, it simply calls the `tf.matmul()` function, so the
# following lines are equivalent:
d = a @ b @ [[10.], [11.]]
d = tf.matmul(tf.matmul(a, b), [[10.], [11.]])
```

#### Args:

* <b>`a`</b>: `Tensor` of type `float16`, `float32`, `float64`, `int32`, `complex64`,
    `complex128` and rank > 1.
* <b>`b`</b>: `Tensor` with same type and rank as `a`.
* <b>`transpose_a`</b>: If `True`, `a` is transposed before multiplication.
* <b>`transpose_b`</b>: If `True`, `b` is transposed before multiplication.
* <b>`adjoint_a`</b>: If `True`, `a` is conjugated and transposed before
    multiplication.
* <b>`adjoint_b`</b>: If `True`, `b` is conjugated and transposed before
    multiplication.
* <b>`a_is_sparse`</b>: If `True`, `a` is treated as a sparse matrix.
* <b>`b_is_sparse`</b>: If `True`, `b` is treated as a sparse matrix.
* <b>`name`</b>: Name for the operation (optional).


#### Returns:

A `Tensor` of the same type as `a` and `b` where each inner-most matrix is
the product of the corresponding matrices in `a` and `b`, e.g. if all
transpose or adjoint attributes are `False`:

`output`[..., i, j] = sum_k (`a`[..., i, k] * `b`[..., k, j]),
for all indices i, j.

* <b>`Note`</b>: This is matrix product, not element-wise product.



#### Raises:

* <b>`ValueError`</b>: If transpose_a and adjoint_a, or transpose_b and adjoint_b
    are both set to True.

<h3 id="__mod__"><code>__mod__</code></h3>

``` python
__mod__(
    x,
    y
)
```

Returns element-wise remainder of division. When `x < 0` xor `y < 0` is

true, this follows Python semantics in that the result here is consistent
with a flooring divide. E.g. `floor(x / y) * y + mod(x, y) = x`.

*NOTE*: `FloorMod` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`, `float32`, `float64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

<h3 id="__mul__"><code>__mul__</code></h3>

``` python
__mul__(
    x,
    y
)
```

Dispatches cwise mul for "Dense*Dense" and "Dense*Sparse".

<h3 id="__neg__"><code>__neg__</code></h3>

``` python
__neg__(
    x,
    name=None
)
```

Computes numerical negative value element-wise.

I.e., \\(y = -x\\).

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

<h3 id="__nonzero__"><code>__nonzero__</code></h3>

``` python
__nonzero__()
```

Dummy method to prevent a tensor from being used as a Python `bool`.

This is the Python 2.x counterpart to `__bool__()` above.

#### Raises:

`TypeError`.

<h3 id="__or__"><code>__or__</code></h3>

``` python
__or__(
    x,
    y
)
```

Returns the truth value of x OR y element-wise.

*NOTE*: `LogicalOr` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`y`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

<h3 id="__pow__"><code>__pow__</code></h3>

``` python
__pow__(
    x,
    y
)
```

Computes the power of one value to another.

Given a tensor `x` and a tensor `y`, this operation computes \\(x^y\\) for
corresponding elements in `x` and `y`. For example:

```python
x = tf.constant([[2, 2], [3, 3]])
y = tf.constant([[8, 16], [2, 3]])
tf.pow(x, y)  # [[256, 65536], [9, 27]]
```

#### Args:

* <b>`x`</b>: A `Tensor` of type `float32`, `float64`, `int32`, `int64`, `complex64`,
   or `complex128`.
* <b>`y`</b>: A `Tensor` of type `float32`, `float64`, `int32`, `int64`, `complex64`,
   or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`.

<h3 id="__radd__"><code>__radd__</code></h3>

``` python
__radd__(
    y,
    x
)
```

Returns x + y element-wise.

*NOTE*: `Add` supports broadcasting. `AddN` does not. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `half`, `float32`, `float64`, `uint8`, `int8`, `int16`, `int32`, `int64`, `complex64`, `complex128`, `string`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

<h3 id="__rand__"><code>__rand__</code></h3>

``` python
__rand__(
    y,
    x
)
```

Returns the truth value of x AND y element-wise.

*NOTE*: `LogicalAnd` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`y`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

<h3 id="__rdiv__"><code>__rdiv__</code></h3>

``` python
__rdiv__(
    y,
    x
)
```

Divide two values using Python 2 semantics. Used for Tensor.__div__.

#### Args:

* <b>`x`</b>: `Tensor` numerator of real numeric type.
* <b>`y`</b>: `Tensor` denominator of real numeric type.
* <b>`name`</b>: A name for the operation (optional).

#### Returns:

`x / y` returns the quotient of x and y.

<h3 id="__rfloordiv__"><code>__rfloordiv__</code></h3>

``` python
__rfloordiv__(
    y,
    x
)
```

Divides `x / y` elementwise, rounding toward the most negative integer.

The same as `tf.div(x,y)` for integers, but uses `tf.floor(tf.div(x,y))` for
floating point arguments so that the result is always an integer (though
possibly an integer represented as floating point).  This op is generated by
`x // y` floor division in Python 3 and in Python 2.7 with
`from __future__ import division`.

Note that for efficiency, `floordiv` uses C semantics for negative numbers
(unlike Python and Numpy).

`x` and `y` must have the same type, and the result will have the same type
as well.

#### Args:

* <b>`x`</b>: `Tensor` numerator of real numeric type.
* <b>`y`</b>: `Tensor` denominator of real numeric type.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

`x / y` rounded down (except possibly towards zero for negative integers).


#### Raises:

* <b>`TypeError`</b>: If the inputs are complex.

<h3 id="__rmatmul__"><code>__rmatmul__</code></h3>

``` python
__rmatmul__(
    y,
    x
)
```

Multiplies matrix `a` by matrix `b`, producing `a` * `b`.

The inputs must, following any transpositions, be tensors of rank >= 2
where the inner 2 dimensions specify valid matrix multiplication arguments,
and any further outer dimensions match.

Both matrices must be of the same type. The supported types are:
`float16`, `float32`, `float64`, `int32`, `complex64`, `complex128`.

Either matrix can be transposed or adjointed (conjugated and transposed) on
the fly by setting one of the corresponding flag to `True`. These are `False`
by default.

If one or both of the matrices contain a lot of zeros, a more efficient
multiplication algorithm can be used by setting the corresponding
`a_is_sparse` or `b_is_sparse` flag to `True`. These are `False` by default.
This optimization is only available for plain matrices (rank-2 tensors) with
datatypes `bfloat16` or `float32`.

For example:

```python
# 2-D tensor `a`
# [[1, 2, 3],
#  [4, 5, 6]]
a = tf.constant([1, 2, 3, 4, 5, 6], shape=[2, 3])

# 2-D tensor `b`
# [[ 7,  8],
#  [ 9, 10],
#  [11, 12]]
b = tf.constant([7, 8, 9, 10, 11, 12], shape=[3, 2])

# `a` * `b`
# [[ 58,  64],
#  [139, 154]]
c = tf.matmul(a, b)


# 3-D tensor `a`
# [[[ 1,  2,  3],
#   [ 4,  5,  6]],
#  [[ 7,  8,  9],
#   [10, 11, 12]]]
a = tf.constant(np.arange(1, 13, dtype=np.int32),
                shape=[2, 2, 3])

# 3-D tensor `b`
# [[[13, 14],
#   [15, 16],
#   [17, 18]],
#  [[19, 20],
#   [21, 22],
#   [23, 24]]]
b = tf.constant(np.arange(13, 25, dtype=np.int32),
                shape=[2, 3, 2])

# `a` * `b`
# [[[ 94, 100],
#   [229, 244]],
#  [[508, 532],
#   [697, 730]]]
c = tf.matmul(a, b)

# Since python >= 3.5 the @ operator is supported (see PEP 465).
# In TensorFlow, it simply calls the `tf.matmul()` function, so the
# following lines are equivalent:
d = a @ b @ [[10.], [11.]]
d = tf.matmul(tf.matmul(a, b), [[10.], [11.]])
```

#### Args:

* <b>`a`</b>: `Tensor` of type `float16`, `float32`, `float64`, `int32`, `complex64`,
    `complex128` and rank > 1.
* <b>`b`</b>: `Tensor` with same type and rank as `a`.
* <b>`transpose_a`</b>: If `True`, `a` is transposed before multiplication.
* <b>`transpose_b`</b>: If `True`, `b` is transposed before multiplication.
* <b>`adjoint_a`</b>: If `True`, `a` is conjugated and transposed before
    multiplication.
* <b>`adjoint_b`</b>: If `True`, `b` is conjugated and transposed before
    multiplication.
* <b>`a_is_sparse`</b>: If `True`, `a` is treated as a sparse matrix.
* <b>`b_is_sparse`</b>: If `True`, `b` is treated as a sparse matrix.
* <b>`name`</b>: Name for the operation (optional).


#### Returns:

A `Tensor` of the same type as `a` and `b` where each inner-most matrix is
the product of the corresponding matrices in `a` and `b`, e.g. if all
transpose or adjoint attributes are `False`:

`output`[..., i, j] = sum_k (`a`[..., i, k] * `b`[..., k, j]),
for all indices i, j.

* <b>`Note`</b>: This is matrix product, not element-wise product.



#### Raises:

* <b>`ValueError`</b>: If transpose_a and adjoint_a, or transpose_b and adjoint_b
    are both set to True.

<h3 id="__rmod__"><code>__rmod__</code></h3>

``` python
__rmod__(
    y,
    x
)
```

Returns element-wise remainder of division. When `x < 0` xor `y < 0` is

true, this follows Python semantics in that the result here is consistent
with a flooring divide. E.g. `floor(x / y) * y + mod(x, y) = x`.

*NOTE*: `FloorMod` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`, `float32`, `float64`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

<h3 id="__rmul__"><code>__rmul__</code></h3>

``` python
__rmul__(
    y,
    x
)
```

Dispatches cwise mul for "Dense*Dense" and "Dense*Sparse".

<h3 id="__ror__"><code>__ror__</code></h3>

``` python
__ror__(
    y,
    x
)
```

Returns the truth value of x OR y element-wise.

*NOTE*: `LogicalOr` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor` of type `bool`.
* <b>`y`</b>: A `Tensor` of type `bool`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

<h3 id="__rpow__"><code>__rpow__</code></h3>

``` python
__rpow__(
    y,
    x
)
```

Computes the power of one value to another.

Given a tensor `x` and a tensor `y`, this operation computes \\(x^y\\) for
corresponding elements in `x` and `y`. For example:

```python
x = tf.constant([[2, 2], [3, 3]])
y = tf.constant([[8, 16], [2, 3]])
tf.pow(x, y)  # [[256, 65536], [9, 27]]
```

#### Args:

* <b>`x`</b>: A `Tensor` of type `float32`, `float64`, `int32`, `int64`, `complex64`,
   or `complex128`.
* <b>`y`</b>: A `Tensor` of type `float32`, `float64`, `int32`, `int64`, `complex64`,
   or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`.

<h3 id="__rsub__"><code>__rsub__</code></h3>

``` python
__rsub__(
    y,
    x
)
```

Returns x - y element-wise.

*NOTE*: `Sub` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `half`, `float32`, `float64`, `uint8`, `int8`, `uint16`, `int16`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

<h3 id="__rtruediv__"><code>__rtruediv__</code></h3>

``` python
__rtruediv__(
    y,
    x
)
```



<h3 id="__rxor__"><code>__rxor__</code></h3>

``` python
__rxor__(
    y,
    x
)
```

x ^ y = (x | y) & ~(x & y).

<h3 id="__sub__"><code>__sub__</code></h3>

``` python
__sub__(
    x,
    y
)
```

Returns x - y element-wise.

*NOTE*: `Sub` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `half`, `float32`, `float64`, `uint8`, `int8`, `uint16`, `int16`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.

<h3 id="__truediv__"><code>__truediv__</code></h3>

``` python
__truediv__(
    x,
    y
)
```



<h3 id="__xor__"><code>__xor__</code></h3>

``` python
__xor__(
    x,
    y
)
```

x ^ y = (x | y) & ~(x & y).

<h3 id="consumers"><code>consumers</code></h3>

``` python
consumers()
```

Returns a list of `Operation`s that consume this tensor.

#### Returns:

A list of `Operation`s.

<h3 id="eval"><code>eval</code></h3>

``` python
eval(
    feed_dict=None,
    session=None
)
```

Evaluates this tensor in a `Session`.

Calling this method will execute all preceding operations that
produce the inputs needed for the operation that produces this
tensor.

*N.B.* Before invoking `Tensor.eval()`, its graph must have been
launched in a session, and either a default session must be
available, or `session` must be specified explicitly.

#### Args:

* <b>`feed_dict`</b>: A dictionary that maps `Tensor` objects to feed values.
    See [`tf.Session.run`](../tf/Session.md#run) for a
    description of the valid feed values.
* <b>`session`</b>: (Optional.) The `Session` to be used to evaluate this tensor. If
    none, the default session will be used.


#### Returns:

A numpy array corresponding to the value of this tensor.

<h3 id="get_shape"><code>get_shape</code></h3>

``` python
get_shape()
```

Alias of Tensor.shape.

<h3 id="set_shape"><code>set_shape</code></h3>

``` python
set_shape(shape)
```

Updates the shape of this tensor.

This method can be called multiple times, and will merge the given
`shape` with the current shape of this tensor. It can be used to
provide additional information about the shape of this tensor that
cannot be inferred from the graph alone. For example, this can be used
to provide additional information about the shapes of images:

```python
_, image_data = tf.TFRecordReader(...).read(...)
image = tf.image.decode_png(image_data, channels=3)

# The height and width dimensions of `image` are data dependent, and
# cannot be computed without executing the op.
print(image.shape)
==> TensorShape([Dimension(None), Dimension(None), Dimension(3)])

# We know that each image in this dataset is 28 x 28 pixels.
image.set_shape([28, 28, 3])
print(image.shape)
==> TensorShape([Dimension(28), Dimension(28), Dimension(3)])
```

#### Args:

* <b>`shape`</b>: A `TensorShape` representing the shape of this tensor.


#### Raises:

* <b>`ValueError`</b>: If `shape` is not compatible with the current shape of
    this tensor.



## Class Members

<h3 id="OVERLOADABLE_OPERATORS"><code>OVERLOADABLE_OPERATORS</code></h3>

<h3 id="__array_priority__"><code>__array_priority__</code></h3>

