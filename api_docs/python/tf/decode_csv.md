<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.decode_csv" />
</div>

# tf.decode_csv

``` python
decode_csv(
    records,
    record_defaults,
    field_delim=',',
    use_quote_delim=True,
    name=None,
    na_value=''
)
```



Defined in [`tensorflow/python/ops/parsing_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/parsing_ops.py).

See the guides: [Inputs and Readers > Converting](../../../api_guides/python/io_ops.md#Converting), [Reading data > Reading from files](../../../api_guides/python/reading_data.md#Reading_from_files), [Strings > Conversion](../../../api_guides/python/string_ops.md#Conversion)

Convert CSV records to tensors. Each column maps to one tensor.

RFC 4180 format is expected for the CSV records.
(https://tools.ietf.org/html/rfc4180)
Note that we allow leading and trailing spaces with int or float field.

#### Args:

* <b>`records`</b>: A `Tensor` of type `string`.
    Each string is a record/row in the csv and all records should have
    the same format.
* <b>`record_defaults`</b>: A list of `Tensor` objects with specific types.
    Acceptable types are `float32`, `int32`, `int64`, `string`.
    One tensor per column of the input record, with either a
    scalar default value for that column or empty if the column is required.
* <b>`field_delim`</b>: An optional `string`. Defaults to `","`.
    char delimiter to separate fields in a record.
* <b>`use_quote_delim`</b>: An optional `bool`. Defaults to `True`.
    If false, treats double quotation marks as regular
    characters inside of the string fields (ignoring RFC 4180, Section 2,
    Bullet 5).
* <b>`name`</b>: A name for the operation (optional).
* <b>`na_value`</b>: Additional string to recognize as NA/NaN.


#### Returns:

A list of `Tensor` objects. Has the same type as `record_defaults`.
Each tensor will have the same shape as records.