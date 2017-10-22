<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.Print" />
</div>

# tf.Print

``` python
Print(
    input_,
    data,
    message=None,
    first_n=None,
    summarize=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/logging_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/logging_ops.py).

See the guide: [Control Flow > Debugging Operations](../../../api_guides/python/control_flow_ops.md#Debugging_Operations)

Prints a list of tensors.

This is an identity op with the side effect of printing `data` when
evaluating.

Note: This op prints to the standard error. It is not currently compatible
  with jupyter notebook (printing to the notebook *server's* output, not into
  the notebook).

#### Args:

* <b>`input_`</b>: A tensor passed through this op.
* <b>`data`</b>: A list of tensors to print out when op is evaluated.
* <b>`message`</b>: A string, prefix of the error message.
* <b>`first_n`</b>: Only log `first_n` number of times. Negative numbers log always;
           this is the default.
* <b>`summarize`</b>: Only print this many entries of each tensor. If None, then a
             maximum of 3 elements are printed per input tensor.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

Same tensor as `input_`.