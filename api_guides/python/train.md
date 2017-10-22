<!-- DO NOT EDIT! Automatically generated file. -->
# Training
[TOC]

[`tf.train`](../../api_docs/python/tf/train.md) provides a set of classes and functions that help train models.

<h2 id="Optimizers">Optimizers</h2>

The Optimizer base class provides methods to compute gradients for a loss and
apply gradients to variables.  A collection of subclasses implement classic
optimization algorithms such as GradientDescent and Adagrad.

You never instantiate the Optimizer class itself, but instead instantiate one
of the subclasses.

*   [`tf.train.Optimizer`](../../api_docs/python/tf/train/Optimizer.md)
*   [`tf.train.GradientDescentOptimizer`](../../api_docs/python/tf/train/GradientDescentOptimizer.md)
*   [`tf.train.AdadeltaOptimizer`](../../api_docs/python/tf/train/AdadeltaOptimizer.md)
*   [`tf.train.AdagradOptimizer`](../../api_docs/python/tf/train/AdagradOptimizer.md)
*   [`tf.train.AdagradDAOptimizer`](../../api_docs/python/tf/train/AdagradDAOptimizer.md)
*   [`tf.train.MomentumOptimizer`](../../api_docs/python/tf/train/MomentumOptimizer.md)
*   [`tf.train.AdamOptimizer`](../../api_docs/python/tf/train/AdamOptimizer.md)
*   [`tf.train.FtrlOptimizer`](../../api_docs/python/tf/train/FtrlOptimizer.md)
*   [`tf.train.ProximalGradientDescentOptimizer`](../../api_docs/python/tf/train/ProximalGradientDescentOptimizer.md)
*   [`tf.train.ProximalAdagradOptimizer`](../../api_docs/python/tf/train/ProximalAdagradOptimizer.md)
*   [`tf.train.RMSPropOptimizer`](../../api_docs/python/tf/train/RMSPropOptimizer.md)

<h2 id="Gradient_Computation">Gradient Computation</h2>

TensorFlow provides functions to compute the derivatives for a given
TensorFlow computation graph, adding operations to the graph. The
optimizer classes automatically compute derivatives on your graph, but
creators of new Optimizers or expert users can call the lower-level
functions below.

*   [`tf.gradients`](../../api_docs/python/tf/gradients.md)
*   [`tf.AggregationMethod`](../../api_docs/python/tf/AggregationMethod.md)
*   [`tf.stop_gradient`](../../api_docs/python/tf/stop_gradient.md)
*   [`tf.hessians`](../../api_docs/python/tf/hessians.md)


<h2 id="Gradient_Clipping">Gradient Clipping</h2>

TensorFlow provides several operations that you can use to add clipping
functions to your graph. You can use these functions to perform general data
clipping, but they're particularly useful for handling exploding or vanishing
gradients.

*   [`tf.clip_by_value`](../../api_docs/python/tf/clip_by_value.md)
*   [`tf.clip_by_norm`](../../api_docs/python/tf/clip_by_norm.md)
*   [`tf.clip_by_average_norm`](../../api_docs/python/tf/clip_by_average_norm.md)
*   [`tf.clip_by_global_norm`](../../api_docs/python/tf/clip_by_global_norm.md)
*   [`tf.global_norm`](../../api_docs/python/tf/global_norm.md)

<h2 id="Decaying_the_learning_rate">Decaying the learning rate</h2>
*   [`tf.train.exponential_decay`](../../api_docs/python/tf/train/exponential_decay.md)
*   [`tf.train.inverse_time_decay`](../../api_docs/python/tf/train/inverse_time_decay.md)
*   [`tf.train.natural_exp_decay`](../../api_docs/python/tf/train/natural_exp_decay.md)
*   [`tf.train.piecewise_constant`](../../api_docs/python/tf/train/piecewise_constant.md)
*   [`tf.train.polynomial_decay`](../../api_docs/python/tf/train/polynomial_decay.md)

<h2 id="Moving_Averages">Moving Averages</h2>

Some training algorithms, such as GradientDescent and Momentum often benefit
from maintaining a moving average of variables during optimization.  Using the
moving averages for evaluations often improve results significantly.

*   [`tf.train.ExponentialMovingAverage`](../../api_docs/python/tf/train/ExponentialMovingAverage.md)

<h2 id="Coordinator_and_QueueRunner">Coordinator and QueueRunner</h2>

See [Threading and Queues](../../api_guides/python/threading_and_queues.md)
for how to use threads and queues.  For documentation on the Queue API,
see [Queues](../../api_guides/python/io_ops.md#queues).


*   [`tf.train.Coordinator`](../../api_docs/python/tf/train/Coordinator.md)
*   [`tf.train.QueueRunner`](../../api_docs/python/tf/train/QueueRunner.md)
*   [`tf.train.LooperThread`](../../api_docs/python/tf/train/LooperThread.md)
*   [`tf.train.add_queue_runner`](../../api_docs/python/tf/train/add_queue_runner.md)
*   [`tf.train.start_queue_runners`](../../api_docs/python/tf/train/start_queue_runners.md)

<h2 id="Distributed_execution">Distributed execution</h2>

See [Distributed TensorFlow](../../deploy/distributed.md) for
more information about how to configure a distributed TensorFlow program.

*   [`tf.train.Server`](../../api_docs/python/tf/train/Server.md)
*   [`tf.train.Supervisor`](../../api_docs/python/tf/train/Supervisor.md)
*   [`tf.train.SessionManager`](../../api_docs/python/tf/train/SessionManager.md)
*   [`tf.train.ClusterSpec`](../../api_docs/python/tf/train/ClusterSpec.md)
*   [`tf.train.replica_device_setter`](../../api_docs/python/tf/train/replica_device_setter.md)
*   [`tf.train.MonitoredTrainingSession`](../../api_docs/python/tf/train/MonitoredTrainingSession.md)
*   [`tf.train.MonitoredSession`](../../api_docs/python/tf/train/MonitoredSession.md)
*   [`tf.train.SingularMonitoredSession`](../../api_docs/python/tf/train/SingularMonitoredSession.md)
*   [`tf.train.Scaffold`](../../api_docs/python/tf/train/Scaffold.md)
*   [`tf.train.SessionCreator`](../../api_docs/python/tf/train/SessionCreator.md)
*   [`tf.train.ChiefSessionCreator`](../../api_docs/python/tf/train/ChiefSessionCreator.md)
*   [`tf.train.WorkerSessionCreator`](../../api_docs/python/tf/train/WorkerSessionCreator.md)

<h2 id="Reading_Summaries_from_Event_Files">Reading Summaries from Event Files</h2>

See [Summaries and TensorBoard](../../get_started/summaries_and_tensorboard.md) for an
overview of summaries, event files, and visualization in TensorBoard.

*   [`tf.train.summary_iterator`](../../api_docs/python/tf/train/summary_iterator.md)

<h2 id="Training_Hooks">Training Hooks</h2>

Hooks are tools that run in the process of training/evaluation of the model.

*   [`tf.train.SessionRunHook`](../../api_docs/python/tf/train/SessionRunHook.md)
*   [`tf.train.SessionRunArgs`](../../api_docs/python/tf/train/SessionRunArgs.md)
*   [`tf.train.SessionRunContext`](../../api_docs/python/tf/train/SessionRunContext.md)
*   [`tf.train.SessionRunValues`](../../api_docs/python/tf/train/SessionRunValues.md)
*   [`tf.train.LoggingTensorHook`](../../api_docs/python/tf/train/LoggingTensorHook.md)
*   [`tf.train.StopAtStepHook`](../../api_docs/python/tf/train/StopAtStepHook.md)
*   [`tf.train.CheckpointSaverHook`](../../api_docs/python/tf/train/CheckpointSaverHook.md)
*   [`tf.train.NewCheckpointReader`](../../api_docs/python/tf/train/NewCheckpointReader.md)
*   [`tf.train.StepCounterHook`](../../api_docs/python/tf/train/StepCounterHook.md)
*   [`tf.train.NanLossDuringTrainingError`](../../api_docs/python/tf/train/NanLossDuringTrainingError.md)
*   [`tf.train.NanTensorHook`](../../api_docs/python/tf/train/NanTensorHook.md)
*   [`tf.train.SummarySaverHook`](../../api_docs/python/tf/train/SummarySaverHook.md)
*   [`tf.train.GlobalStepWaiterHook`](../../api_docs/python/tf/train/GlobalStepWaiterHook.md)
*   [`tf.train.FinalOpsHook`](../../api_docs/python/tf/train/FinalOpsHook.md)
*   [`tf.train.FeedFnHook`](../../api_docs/python/tf/train/FeedFnHook.md)

<h2 id="Training_Utilities">Training Utilities</h2>

*   [`tf.train.global_step`](../../api_docs/python/tf/train/global_step.md)
*   [`tf.train.basic_train_loop`](../../api_docs/python/tf/train/basic_train_loop.md)
*   [`tf.train.get_global_step`](../../api_docs/python/tf/train/get_global_step.md)
*   [`tf.train.assert_global_step`](../../api_docs/python/tf/train/assert_global_step.md)
*   [`tf.train.write_graph`](../../api_docs/python/tf/train/write_graph.md)
