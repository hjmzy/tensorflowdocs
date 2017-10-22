<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tfdbg.load_tensor_from_event_file" />
</div>

# tfdbg.load_tensor_from_event_file

``` python
load_tensor_from_event_file(event_file_path)
```



Defined in [`tensorflow/python/debug/lib/debug_data.py`](https://www.tensorflow.org/code/tensorflow/python/debug/lib/debug_data.py).

See the guide: [TensorFlow Debugger > Functions for loading debug-dump data](../../../api_guides/python/tfdbg.md#Functions_for_loading_debug_dump_data)

Load a tensor from an event file.

Assumes that the event file contains a `Event` protobuf and the `Event`
protobuf contains a `Tensor` value.

#### Args:

* <b>`event_file_path`</b>: (`str`) path to the event file.


#### Returns:

The tensor value loaded from the event file, as a `numpy.ndarray`. For
uninitialized Tensors, returns `None`. For Tensors of data types that
cannot be converted to `numpy.ndarray` (e.g., `tf.resource`), return
`None`.