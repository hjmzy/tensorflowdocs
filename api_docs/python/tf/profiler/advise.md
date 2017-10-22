<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.profiler.advise" />
</div>

# tf.profiler.advise

``` python
advise(
    graph,
    run_meta=None,
    options=_DEFAULT_ADVISE_OPTIONS
)
```



Defined in [`tensorflow/python/profiler/model_analyzer.py`](https://www.tensorflow.org/code/tensorflow/python/profiler/model_analyzer.py).

Auto profile and advise.

  Builds profiles and automatically check anomalies of various
  aspects. For more details:
  https://github.com/tensorflow/tensorflow/tree/master/tensorflow/core/profiler/README.md

#### Args:

* <b>`graph`</b>: required tf.Graph.
* <b>`run_meta`</b>: optional tensorflow.RunMetadata proto. It is necessary to
      to support run time information profiling, such as time and memory.
* <b>`options`</b>: see ALL_ADVICE example above. Default checks everything.

#### Returns:

Returns AdviceProto proto