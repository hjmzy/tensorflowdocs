<!-- DO NOT EDIT! Automatically generated file. -->
# TensorFlow Debugger
[TOC]

Public Python API of TensorFlow Debugger (tfdbg).

<h2 id="Functions_for_adding_debug_watches">Functions for adding debug watches</h2>

These functions help you modify `RunOptions` to specify which `Tensor`s are to
be watched when the TensorFlow graph is executed at runtime.

*   [`tfdbg.add_debug_tensor_watch`](../../api_docs/python/tfdbg/add_debug_tensor_watch.md)
*   [`tfdbg.watch_graph`](../../api_docs/python/tfdbg/watch_graph.md)
*   [`tfdbg.watch_graph_with_blacklists`](../../api_docs/python/tfdbg/watch_graph_with_blacklists.md)


<h2 id="Classes_for_debug_dump_data_and_directories">Classes for debug-dump data and directories</h2>

These classes allow you to load and inspect tensor values dumped from
TensorFlow graphs during runtime.

*   [`tfdbg.DebugTensorDatum`](../../api_docs/python/tfdbg/DebugTensorDatum.md)
*   [`tfdbg.DebugDumpDir`](../../api_docs/python/tfdbg/DebugDumpDir.md)


<h2 id="Functions_for_loading_debug_dump_data">Functions for loading debug-dump data</h2>

*   [`tfdbg.load_tensor_from_event_file`](../../api_docs/python/tfdbg/load_tensor_from_event_file.md)


<h2 id="Tensor_value_predicates">Tensor-value predicates</h2>

Built-in tensor-filter predicates to support conditional breakpoint between
runs. See `DebugDumpDir.find()` for more details.

*   [`tfdbg.has_inf_or_nan`](../../api_docs/python/tfdbg/has_inf_or_nan.md)


<h2 id="Session_wrapper_class_and_SessionRunHook_implementations">Session wrapper class and `SessionRunHook` implementations</h2>

These classes allow you to

* wrap aroundTensorFlow `Session` objects to debug plain TensorFlow models
  (see `DumpingDebugWrapperSession` and `LocalCLIDebugWrapperSession`), or
* generate `SessionRunHook` objects to debug `tf.contrib.learn` models (see
  `DumpingDebugHook` and `LocalCLIDebugHook`).

*   [`tfdbg.DumpingDebugHook`](../../api_docs/python/tfdbg/DumpingDebugHook.md)
*   [`tfdbg.DumpingDebugWrapperSession`](../../api_docs/python/tfdbg/DumpingDebugWrapperSession.md)
*   [`tfdbg.LocalCLIDebugHook`](../../api_docs/python/tfdbg/LocalCLIDebugHook.md)
*   [`tfdbg.LocalCLIDebugWrapperSession`](../../api_docs/python/tfdbg/LocalCLIDebugWrapperSession.md)
