<!-- DO NOT EDIT! Automatically generated file. -->
# Performance

Performance is often a significant issue when training a machine learning
model.  This section explains various ways to optimize performance.  Start
your investigation with the [Performance Guide](../performance/performance_guide.md) and then go
deeper with techniques detailed in [High-Performance Models](../performance/performance_models.md):

  * [Performance Guide](../performance/performance_guide.md), which contains a collection of best
    practices for optimizing your TensorFlow code.

  * [High-Performance Models](../performance/performance_models.md), which contains a collection
    of advanced techniques to build highly scalable models targeting different
    system types and network topologies.

  * [Benchmarks](../performance/benchmarks.md), which contains a collection of
    benchmark results.

XLA (Accelerated Linear Algebra) is an experimental compiler for linear
algebra that optimizes TensorFlow computations. The following guides explore
XLA:

  * [XLA Overview](../performance/xla/index.md), which introduces XLA.
  * [Broadcasting Semantics](../performance/xla/broadcasting.md), which describes XLA's
    broadcasting semantics.
  * [Developing a new back end for XLA](../performance/xla/developing_new_backend.md), which
    explains how to re-target TensorFlow in order to optimize the performance
    of the computational graph for particular hardware.
  * [Using JIT Compilation](../performance/xla/jit.md), which describes the XLA JIT compiler that
    compiles and runs parts of TensorFlow graphs via XLA in order to optimize
    performance.
  * [Operation Semantics](../performance/xla/operation_semantics.md), which is a reference manual
    describing the semantics of operations in the `ComputationBuilder`
    interface.
  * [Shapes and Layout](../performance/xla/shapes.md), which details the `Shape` protocol buffer.
  * [Using AOT compilation](../performance/xla/tfcompile.md), which explains `tfcompile`, a
    standalone tool that compiles TensorFlow graphs into executable code in
    order to optimize performance.

And finally, we offer the following guide:

  * [How to Quantize Neural Networks with TensorFlow](../performance/quantization.md), which
    can explains how to use quantization to reduce model size, both in storage
    and at runtime. Quantization can improve performance, especially on
    mobile hardware.

