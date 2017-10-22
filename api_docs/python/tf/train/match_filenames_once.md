<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.match_filenames_once" />
</div>

# tf.train.match_filenames_once

``` python
match_filenames_once(
    pattern,
    name=None
)
```



Defined in [`tensorflow/python/training/input.py`](https://www.tensorflow.org/code/tensorflow/python/training/input.py).

See the guides: [Inputs and Readers > Input pipeline](../../../../api_guides/python/io_ops.md#Input_pipeline), [Reading data > Reading from files](../../../../api_guides/python/reading_data.md#Reading_from_files)

Save the list of files matching pattern, so it is only computed once.

#### Args:

* <b>`pattern`</b>: A file pattern (glob), or 1D tensor of file patterns.
* <b>`name`</b>: A name for the operations (optional).


#### Returns:

A variable that is initialized to the list of files matching the pattern(s).