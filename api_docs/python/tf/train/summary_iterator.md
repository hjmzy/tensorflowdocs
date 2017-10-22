<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.summary_iterator" />
</div>

# tf.train.summary_iterator

``` python
summary_iterator(path)
```



Defined in [`tensorflow/python/summary/summary_iterator.py`](https://www.tensorflow.org/code/tensorflow/python/summary/summary_iterator.py).

See the guide: [Training > Reading Summaries from Event Files](../../../../api_guides/python/train.md#Reading_Summaries_from_Event_Files)

An iterator for reading `Event` protocol buffers from an event file.

You can use this function to read events written to an event file. It returns
a Python iterator that yields `Event` protocol buffers.

Example: Print the contents of an events file.

```python
for e in tf.train.summary_iterator(path to events file):
    print(e)
```

Example: Print selected summary values.

```python
# This example supposes that the events file contains summaries with a
# summary value tag 'loss'.  These could have been added by calling
# `add_summary()`, passing the output of a scalar summary op created with
# with: `tf.summary.scalar('loss', loss_tensor)`.
for e in tf.train.summary_iterator(path to events file):
    for v in e.summary.value:
        if v.tag == 'loss':
            print(v.simple_value)
```

See the protocol buffer definitions of
[Event](https://www.tensorflow.org/code/tensorflow/core/util/event.proto)
and
[Summary](https://www.tensorflow.org/code/tensorflow/core/framework/summary.proto)
for more information about their attributes.

#### Args:

* <b>`path`</b>: The path to an event file created by a `SummaryWriter`.


#### Yields:

`Event` protocol buffers.