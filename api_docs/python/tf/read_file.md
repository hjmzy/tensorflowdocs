<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.read_file" />
</div>

# tf.read_file

``` python
read_file(
    filename,
    name=None
)
```



Defined in `tensorflow/python/ops/gen_io_ops.py`.

See the guide: [Inputs and Readers > Dealing with the filesystem](../../../api_guides/python/io_ops.md#Dealing_with_the_filesystem)

Reads and outputs the entire contents of the input filename.

#### Args:

* <b>`filename`</b>: A `Tensor` of type `string`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `string`.