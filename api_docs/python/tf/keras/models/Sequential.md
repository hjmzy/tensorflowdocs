<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.models.Sequential" />
<meta itemprop="property" content="activity_regularizer"/>
<meta itemprop="property" content="dtype"/>
<meta itemprop="property" content="graph"/>
<meta itemprop="property" content="input"/>
<meta itemprop="property" content="input_mask"/>
<meta itemprop="property" content="input_shape"/>
<meta itemprop="property" content="input_spec"/>
<meta itemprop="property" content="losses"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="non_trainable_variables"/>
<meta itemprop="property" content="non_trainable_weights"/>
<meta itemprop="property" content="output"/>
<meta itemprop="property" content="output_mask"/>
<meta itemprop="property" content="output_shape"/>
<meta itemprop="property" content="regularizers"/>
<meta itemprop="property" content="scope_name"/>
<meta itemprop="property" content="state_updates"/>
<meta itemprop="property" content="stateful"/>
<meta itemprop="property" content="trainable"/>
<meta itemprop="property" content="trainable_variables"/>
<meta itemprop="property" content="trainable_weights"/>
<meta itemprop="property" content="updates"/>
<meta itemprop="property" content="uses_learning_phase"/>
<meta itemprop="property" content="variables"/>
<meta itemprop="property" content="weights"/>
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__deepcopy__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="add"/>
<meta itemprop="property" content="add_loss"/>
<meta itemprop="property" content="add_update"/>
<meta itemprop="property" content="add_variable"/>
<meta itemprop="property" content="add_weight"/>
<meta itemprop="property" content="apply"/>
<meta itemprop="property" content="build"/>
<meta itemprop="property" content="call"/>
<meta itemprop="property" content="compile"/>
<meta itemprop="property" content="compute_mask"/>
<meta itemprop="property" content="count_params"/>
<meta itemprop="property" content="evaluate"/>
<meta itemprop="property" content="evaluate_generator"/>
<meta itemprop="property" content="fit"/>
<meta itemprop="property" content="fit_generator"/>
<meta itemprop="property" content="from_config"/>
<meta itemprop="property" content="get_config"/>
<meta itemprop="property" content="get_input_at"/>
<meta itemprop="property" content="get_input_mask_at"/>
<meta itemprop="property" content="get_input_shape_at"/>
<meta itemprop="property" content="get_layer"/>
<meta itemprop="property" content="get_losses_for"/>
<meta itemprop="property" content="get_output_at"/>
<meta itemprop="property" content="get_output_mask_at"/>
<meta itemprop="property" content="get_output_shape_at"/>
<meta itemprop="property" content="get_updates_for"/>
<meta itemprop="property" content="get_weights"/>
<meta itemprop="property" content="load_weights"/>
<meta itemprop="property" content="pop"/>
<meta itemprop="property" content="predict"/>
<meta itemprop="property" content="predict_classes"/>
<meta itemprop="property" content="predict_generator"/>
<meta itemprop="property" content="predict_on_batch"/>
<meta itemprop="property" content="predict_proba"/>
<meta itemprop="property" content="reset_states"/>
<meta itemprop="property" content="save"/>
<meta itemprop="property" content="save_weights"/>
<meta itemprop="property" content="set_weights"/>
<meta itemprop="property" content="summary"/>
<meta itemprop="property" content="test_on_batch"/>
<meta itemprop="property" content="to_json"/>
<meta itemprop="property" content="to_yaml"/>
<meta itemprop="property" content="train_on_batch"/>
</div>

# tf.keras.models.Sequential

## Class `Sequential`

Inherits From: [`Model`](../../../tf/keras/models/Model.md)



Defined in [`tensorflow/python/keras/_impl/keras/models.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/models.py).

Linear stack of layers.

#### Arguments:

* <b>`layers`</b>: list of layers to add to the model.

# Note
    The first layer passed to a Sequential model
    should have a defined input shape. What that
    means is that it should have received an `input_shape`
    or `batch_input_shape` argument,
    or for some type of layers (recurrent, Dense...)
    an `input_dim` argument.

Example:

    ```python
        model = Sequential()
        # first layer must have a defined input shape
        model.add(Dense(32, input_dim=500))
        # afterwards, Keras does automatic shape inference
        model.add(Dense(32))

        # also possible (equivalent to the above):
        model = Sequential()
        model.add(Dense(32, input_shape=(500,)))
        model.add(Dense(32))

        # also possible (equivalent to the above):
        model = Sequential()
        # here the batch dimension is None,
        # which means any batch size will be accepted by the model.
        model.add(Dense(32, batch_input_shape=(None, 500)))
        model.add(Dense(32))
    ```

## Properties

<h3 id="activity_regularizer"><code>activity_regularizer</code></h3>

Optional regularizer function for the output of this layer.

<h3 id="dtype"><code>dtype</code></h3>



<h3 id="graph"><code>graph</code></h3>



<h3 id="input"><code>input</code></h3>

Retrieves the input tensor(s) of a layer.

Only applicable if the layer has exactly one input,
i.e. if it is connected to one incoming layer.

#### Returns:

Input tensor or list of input tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to
    more than one incoming layers.


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.
* <b>`AttributeError`</b>: If no inbound nodes are found.

<h3 id="input_mask"><code>input_mask</code></h3>

Retrieves the input mask tensor(s) of a layer.

Only applicable if the layer has exactly one inbound node,
i.e. if it is connected to one incoming layer.

#### Returns:

Input mask tensor (potentially None) or list of input
mask tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to
    more than one incoming layers.

<h3 id="input_shape"><code>input_shape</code></h3>

Retrieves the input shape(s) of a layer.

Only applicable if the layer has exactly one input,
i.e. if it is connected to one incoming layer, or if all inputs
have the same shape.

#### Returns:

Input shape, as an integer shape tuple
(or list of shape tuples, one tuple per input tensor).


#### Raises:

* <b>`AttributeError`</b>: if the layer has no defined input_shape.
* <b>`RuntimeError`</b>: if called in Eager mode.

<h3 id="input_spec"><code>input_spec</code></h3>

Gets the network's input specs.

#### Returns:

A list of `InputSpec` instances (one per input to the model)
    or a single instance if the model has only one input.

<h3 id="losses"><code>losses</code></h3>



<h3 id="name"><code>name</code></h3>



<h3 id="non_trainable_variables"><code>non_trainable_variables</code></h3>



<h3 id="non_trainable_weights"><code>non_trainable_weights</code></h3>



<h3 id="output"><code>output</code></h3>

Retrieves the output tensor(s) of a layer.

Only applicable if the layer has exactly one output,
i.e. if it is connected to one incoming layer.

#### Returns:

Output tensor or list of output tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to more than one incoming
    layers.
* <b>`RuntimeError`</b>: if called in Eager mode.

<h3 id="output_mask"><code>output_mask</code></h3>

Retrieves the output mask tensor(s) of a layer.

Only applicable if the layer has exactly one inbound node,
i.e. if it is connected to one incoming layer.

#### Returns:

Output mask tensor (potentially None) or list of output
mask tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to
    more than one incoming layers.

<h3 id="output_shape"><code>output_shape</code></h3>

Retrieves the output shape(s) of a layer.

Only applicable if the layer has one output,
or if all outputs have the same shape.

#### Returns:

Output shape, as an integer shape tuple
(or list of shape tuples, one tuple per output tensor).


#### Raises:

* <b>`AttributeError`</b>: if the layer has no defined output shape.
* <b>`RuntimeError`</b>: if called in Eager mode.

<h3 id="regularizers"><code>regularizers</code></h3>



<h3 id="scope_name"><code>scope_name</code></h3>



<h3 id="state_updates"><code>state_updates</code></h3>



<h3 id="stateful"><code>stateful</code></h3>



<h3 id="trainable"><code>trainable</code></h3>



<h3 id="trainable_variables"><code>trainable_variables</code></h3>



<h3 id="trainable_weights"><code>trainable_weights</code></h3>



<h3 id="updates"><code>updates</code></h3>



<h3 id="uses_learning_phase"><code>uses_learning_phase</code></h3>



<h3 id="variables"><code>variables</code></h3>

Returns the list of all layer variables/weights.

#### Returns:

A list of variables.

<h3 id="weights"><code>weights</code></h3>

Returns the list of all layer variables/weights.

#### Returns:

A list of variables.



## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    layers=None,
    name=None
)
```



<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    inputs,
    **kwargs
)
```

Wrapper around self.call(), for handling internal references.

If a Keras tensor is passed:
    - We call self._add_inbound_node().
    - If necessary, we `build` the layer to match
        the shape of the input(s).
    - We update the _keras_history of the output tensor(s)
        with the current layer.
        This is done as part of _add_inbound_node().

#### Arguments:

* <b>`inputs`</b>: Can be a tensor or list/tuple of tensors.
* <b>`**kwargs`</b>: Additional keyword arguments to be passed to `call()`.


#### Returns:

Output of the layer's `call` method.


#### Raises:

* <b>`ValueError`</b>: in case the layer is missing shape information
        for its `build` call.

<h3 id="__deepcopy__"><code>__deepcopy__</code></h3>

``` python
__deepcopy__(memo)
```



<h3 id="add"><code>add</code></h3>

``` python
add(layer)
```

Adds a layer instance on top of the layer stack.

#### Arguments:

* <b>`layer`</b>: layer instance.


#### Raises:

* <b>`TypeError`</b>: If `layer` is not a layer instance.
* <b>`ValueError`</b>: In case the `layer` argument does not
        know its input shape.
* <b>`ValueError`</b>: In case the `layer` argument has
        multiple output tensors, or is already connected
        somewhere else (forbidden in `Sequential` models).

<h3 id="add_loss"><code>add_loss</code></h3>

``` python
add_loss(
    losses,
    inputs=None
)
```

Add loss tensor(s), potentially dependent on layer inputs.

Some losses (for instance, activity regularization losses) may be dependent
on the inputs passed when calling a layer. Hence, when reusing a same layer
on different inputs `a` and `b`, some entries in `layer.losses` may be
dependent on `a` and some on `b`. This method automatically keeps track
of dependencies.

The `get_losses_for` method allows to retrieve the losses relevant to a
specific set of inputs.

#### Arguments:

* <b>`losses`</b>: Loss tensor, or list/tuple of tensors.
* <b>`inputs`</b>: Optional input tensor(s) that the loss(es) depend on. Must
    match the `inputs` argument passed to the `__call__` method at the time
    the losses are created. If `None` is passed, the losses are assumed
    to be unconditional, and will apply across all dataflows of the layer
    (e.g. weight regularization losses).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="add_update"><code>add_update</code></h3>

``` python
add_update(
    updates,
    inputs=None
)
```

Add update op(s), potentially dependent on layer inputs.

Weight updates (for instance, the updates of the moving mean and variance
in a BatchNormalization layer) may be dependent on the inputs passed
when calling a layer. Hence, when reusing a same layer on
different inputs `a` and `b`, some entries in `layer.updates` may be
dependent on `a` and some on `b`. This method automatically keeps track
of dependencies.

The `get_updates_for` method allows to retrieve the updates relevant to a
specific set of inputs.

This call is ignored in Eager mode.

#### Arguments:

* <b>`updates`</b>: Update op, or list/tuple of update ops.
* <b>`inputs`</b>: Optional input tensor(s) that the update(s) depend on. Must
    match the `inputs` argument passed to the `__call__` method at the time
    the updates are created. If `None` is passed, the updates are assumed
    to be unconditional, and will apply across all dataflows of the layer.

<h3 id="add_variable"><code>add_variable</code></h3>

``` python
add_variable(
    name,
    shape,
    dtype=None,
    initializer=None,
    regularizer=None,
    trainable=True,
    constraint=None
)
```

Adds a new variable to the layer, or gets an existing one; returns it.

#### Arguments:

* <b>`name`</b>: variable name.
* <b>`shape`</b>: variable shape.
* <b>`dtype`</b>: The type of the variable. Defaults to `self.dtype` or `float32`.
* <b>`initializer`</b>: initializer instance (callable).
* <b>`regularizer`</b>: regularizer instance (callable).
* <b>`trainable`</b>: whether the variable should be part of the layer's
    "trainable_variables" (e.g. variables, biases)
    or "non_trainable_variables" (e.g. BatchNorm mean, stddev).
* <b>`constraint`</b>: constraint instance (callable).


#### Returns:

The created variable.


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode with regularizers.

<h3 id="add_weight"><code>add_weight</code></h3>

``` python
add_weight(
    name,
    shape,
    dtype=None,
    initializer=None,
    regularizer=None,
    trainable=True,
    constraint=None
)
```

Adds a weight variable to the layer.

#### Arguments:

* <b>`name`</b>: String, the name for the weight variable.
* <b>`shape`</b>: The shape tuple of the weight.
* <b>`dtype`</b>: The dtype of the weight.
* <b>`initializer`</b>: An Initializer instance (callable).
* <b>`regularizer`</b>: An optional Regularizer instance.
* <b>`trainable`</b>: A boolean, whether the weight should
        be trained via backprop or not (assuming
        that the layer itself is also trainable).
* <b>`constraint`</b>: An optional Constraint instance.


#### Returns:

The created weight variable.

<h3 id="apply"><code>apply</code></h3>

``` python
apply(
    inputs,
    *args,
    **kwargs
)
```

Apply the layer on a input.

This simply wraps `self.__call__`.

#### Arguments:

* <b>`inputs`</b>: Input tensor(s).
* <b>`*args`</b>: additional positional arguments to be passed to `self.call`.
* <b>`**kwargs`</b>: additional keyword arguments to be passed to `self.call`.


#### Returns:

Output tensor(s).

<h3 id="build"><code>build</code></h3>

``` python
build(input_shape=None)
```



<h3 id="call"><code>call</code></h3>

``` python
call(
    inputs,
    mask=None
)
```



<h3 id="compile"><code>compile</code></h3>

``` python
compile(
    optimizer,
    loss,
    metrics=None,
    sample_weight_mode=None,
    weighted_metrics=None,
    **kwargs
)
```

Configures the learning process.

#### Arguments:

* <b>`optimizer`</b>: str (name of optimizer) or optimizer object.
        See [optimizers](/optimizers).
* <b>`loss`</b>: str (name of objective function) or objective function.
        See [losses](/losses).
* <b>`metrics`</b>: list of metrics to be evaluated by the model
        during training and testing.
        Typically you will use `metrics=['accuracy']`.
        See [metrics](/metrics).
* <b>`sample_weight_mode`</b>: if you need to do timestep-wise
        sample weighting (2D weights), set this to "temporal".
        "None" defaults to sample-wise weights (1D).
* <b>`weighted_metrics`</b>: list of metrics to be evaluated and weighted
         by `sample_weight` or `class_weight` during training and testing.
* <b>`**kwargs`</b>: These are passed into `tf.Session.run`.

Example:
    ```python
        model = Sequential()
        model.add(Dense(32, input_shape=(500,)))
        model.add(Dense(10, activation='softmax'))
        model.compile(optimizer='rmsprop',
                      loss='categorical_crossentropy',
                      metrics=['accuracy'])
    ```

<h3 id="compute_mask"><code>compute_mask</code></h3>

``` python
compute_mask(
    inputs,
    mask
)
```



<h3 id="count_params"><code>count_params</code></h3>

``` python
count_params()
```

Count the total number of scalars composing the weights.

#### Returns:

An integer count.


#### Raises:

* <b>`ValueError`</b>: if the layer isn't yet built
      (in which case its weights aren't yet defined).

<h3 id="evaluate"><code>evaluate</code></h3>

``` python
evaluate(
    x,
    y,
    batch_size=32,
    verbose=1,
    sample_weight=None
)
```

Computes the loss on some input data, batch by batch.

#### Arguments:

* <b>`x`</b>: input data, as a Numpy array or list of Numpy arrays
        (if the model has multiple inputs).
* <b>`y`</b>: labels, as a Numpy array.
* <b>`batch_size`</b>: integer. Number of samples per gradient update.
* <b>`verbose`</b>: verbosity mode, 0 or 1.
* <b>`sample_weight`</b>: sample weights, as a Numpy array.


#### Returns:

Scalar test loss (if the model has no metrics)
or list of scalars (if the model computes other metrics).
The attribute `model.metrics_names` will give you
the display labels for the scalar outputs.


#### Raises:

* <b>`RuntimeError`</b>: if the model was never compiled.

<h3 id="evaluate_generator"><code>evaluate_generator</code></h3>

``` python
evaluate_generator(
    generator,
    steps,
    max_queue_size=10,
    workers=1,
    use_multiprocessing=False,
    **kwargs
)
```

Evaluates the model on a data generator.

The generator should return the same kind of data
as accepted by `test_on_batch`.

#### Arguments:

* <b>`generator`</b>: Generator yielding tuples (inputs, targets)
        or (inputs, targets, sample_weights)
* <b>`steps`</b>: Total number of steps (batches of samples)
        to yield from `generator` before stopping.
* <b>`max_queue_size`</b>: maximum size for the generator queue
* <b>`workers`</b>: maximum number of processes to spin up
* <b>`use_multiprocessing`</b>: if True, use process based threading.
        Note that because this implementation
        relies on multiprocessing, you should not pass
        non picklable arguments to the generator
        as they can't be passed easily to children processes.
* <b>`**kwargs`</b>: support for legacy arguments.


#### Returns:

Scalar test loss (if the model has no metrics)
or list of scalars (if the model computes other metrics).
The attribute `model.metrics_names` will give you
the display labels for the scalar outputs.


#### Raises:

* <b>`RuntimeError`</b>: if the model was never compiled.
* <b>`ValueError`</b>: In case the generator yields
        data in an invalid format.

<h3 id="fit"><code>fit</code></h3>

``` python
fit(
    x,
    y,
    batch_size=32,
    epochs=10,
    verbose=1,
    callbacks=None,
    validation_split=0.0,
    validation_data=None,
    shuffle=True,
    class_weight=None,
    sample_weight=None,
    initial_epoch=0
)
```

Trains the model for a fixed number of epochs.

#### Arguments:

* <b>`x`</b>: input data, as a Numpy array or list of Numpy arrays
        (if the model has multiple inputs).
* <b>`y`</b>: labels, as a Numpy array.
* <b>`batch_size`</b>: integer. Number of samples per gradient update.
* <b>`epochs`</b>: integer, the number of epochs to train the model.
* <b>`verbose`</b>: 0 for no logging to stdout,
        1 for progress bar logging, 2 for one log line per epoch.
* <b>`callbacks`</b>: list of `keras.callbacks.Callback` instances.
        List of callbacks to apply during training.
        See [callbacks](/callbacks).
* <b>`validation_split`</b>: float (0. < x < 1).
        Fraction of the data to use as held-out validation data.
* <b>`validation_data`</b>: tuple (x_val, y_val) or tuple
        (x_val, y_val, val_sample_weights) to be used as held-out
        validation data. Will override validation_split.
* <b>`shuffle`</b>: boolean or str (for 'batch').
        Whether to shuffle the samples at each epoch.
        'batch' is a special option for dealing with the
        limitations of HDF5 data; it shuffles in batch-sized chunks.
* <b>`class_weight`</b>: dictionary mapping classes to a weight value,
        used for scaling the loss function (during training only).
* <b>`sample_weight`</b>: Numpy array of weights for
        the training samples, used for scaling the loss function
        (during training only). You can either pass a flat (1D)
        Numpy array with the same length as the input samples
        (1:1 mapping between weights and samples),
        or in the case of temporal data,
        you can pass a 2D array with shape (samples, sequence_length),
        to apply a different weight to every timestep of every sample.
        In this case you should make sure to specify
        sample_weight_mode="temporal" in compile().
* <b>`initial_epoch`</b>: epoch at which to start training
        (useful for resuming a previous training run)


#### Returns:

A `History` object. Its `History.history` attribute is
a record of training loss values and metrics values
at successive epochs, as well as validation loss values
and validation metrics values (if applicable).


#### Raises:

* <b>`RuntimeError`</b>: if the model was never compiled.

<h3 id="fit_generator"><code>fit_generator</code></h3>

``` python
fit_generator(
    generator,
    steps_per_epoch,
    epochs=1,
    verbose=1,
    callbacks=None,
    validation_data=None,
    validation_steps=None,
    class_weight=None,
    max_queue_size=10,
    workers=1,
    use_multiprocessing=False,
    initial_epoch=0,
    **kwargs
)
```

Fits the model on data generated batch-by-batch by a Python generator.

The generator is run in parallel to the model, for efficiency.
For instance, this allows you to do real-time data augmentation
on images on CPU in parallel to training your model on GPU.

#### Arguments:

* <b>`generator`</b>: A generator.
        The output of the generator must be either
        - a tuple (inputs, targets)
        - a tuple (inputs, targets, sample_weights).
        All arrays should contain the same number of samples.
        The generator is expected to loop over its data
        indefinitely. An epoch finishes when `steps_per_epoch`
        batches have been seen by the model.
* <b>`steps_per_epoch`</b>: Total number of steps (batches of samples)
        to yield from `generator` before declaring one epoch
        finished and starting the next epoch. It should typically
        be equal to the number of unique samples of your dataset
        divided by the batch size.
* <b>`epochs`</b>: Integer, total number of iterations on the data.
* <b>`verbose`</b>: Verbosity mode, 0, 1, or 2.
* <b>`callbacks`</b>: List of callbacks to be called during training.
* <b>`validation_data`</b>: This can be either
        - A generator for the validation data
        - A tuple (inputs, targets)
        - A tuple (inputs, targets, sample_weights).
* <b>`validation_steps`</b>: Only relevant if `validation_data`
        is a generator.
        Number of steps to yield from validation generator
        at the end of every epoch. It should typically
        be equal to the number of unique samples of your
        validation dataset divided by the batch size.
* <b>`class_weight`</b>: Dictionary mapping class indices to a weight
        for the class.
* <b>`max_queue_size`</b>: Maximum size for the generator queue
* <b>`workers`</b>: Maximum number of processes to spin up
* <b>`use_multiprocessing`</b>: If True, use process based threading.
        Note that because
        this implementation relies on multiprocessing,
        you should not pass
        non picklable arguments to the generator
        as they can't be passed
        easily to children processes.
* <b>`initial_epoch`</b>: Epoch at which to start training
        (useful for resuming a previous training run)
* <b>`**kwargs`</b>: support for legacy arguments.


#### Returns:

A `History` object.


#### Raises:

* <b>`RuntimeError`</b>: if the model was never compiled.
* <b>`ValueError`</b>: In case the generator yields
        data in an invalid format.

Example:

```python
    def generate_arrays_from_file(path):
        while 1:
            f = open(path)
            for line in f:
                # create Numpy arrays of input data
                # and labels, from each line in the file
                x, y = process_line(line)
                yield (x, y)
                f.close()

    model.fit_generator(generate_arrays_from_file('/my_file.txt'),
                        steps_per_epoch=1000, epochs=10)
```

<h3 id="from_config"><code>from_config</code></h3>

``` python
@classmethod
from_config(
    cls,
    config,
    custom_objects=None
)
```



<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```



<h3 id="get_input_at"><code>get_input_at</code></h3>

``` python
get_input_at(node_index)
```

Retrieves the input tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A tensor (or list of tensors if the layer has multiple inputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_input_mask_at"><code>get_input_mask_at</code></h3>

``` python
get_input_mask_at(node_index)
```

Retrieves the input mask tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A mask tensor
(or list of tensors if the layer has multiple inputs).

<h3 id="get_input_shape_at"><code>get_input_shape_at</code></h3>

``` python
get_input_shape_at(node_index)
```

Retrieves the input shape(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A shape tuple
(or list of shape tuples if the layer has multiple inputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_layer"><code>get_layer</code></h3>

``` python
get_layer(
    name=None,
    index=None
)
```

Retrieve a layer that is part of the model.

Returns a layer based on either its name (unique)
or its index in the graph. Indices are based on
order of horizontal graph traversal (bottom-up).

#### Arguments:

* <b>`name`</b>: string, name of layer.
* <b>`index`</b>: integer, index of layer.


#### Returns:

A layer instance.

<h3 id="get_losses_for"><code>get_losses_for</code></h3>

``` python
get_losses_for(inputs)
```



<h3 id="get_output_at"><code>get_output_at</code></h3>

``` python
get_output_at(node_index)
```

Retrieves the output tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A tensor (or list of tensors if the layer has multiple outputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_output_mask_at"><code>get_output_mask_at</code></h3>

``` python
get_output_mask_at(node_index)
```

Retrieves the output mask tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A mask tensor
(or list of tensors if the layer has multiple outputs).

<h3 id="get_output_shape_at"><code>get_output_shape_at</code></h3>

``` python
get_output_shape_at(node_index)
```

Retrieves the output shape(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A shape tuple
(or list of shape tuples if the layer has multiple outputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_updates_for"><code>get_updates_for</code></h3>

``` python
get_updates_for(inputs)
```



<h3 id="get_weights"><code>get_weights</code></h3>

``` python
get_weights()
```

Retrieves the weights of the model.

#### Returns:

A flat list of Numpy arrays
(one array per model weight).

<h3 id="load_weights"><code>load_weights</code></h3>

``` python
load_weights(
    filepath,
    by_name=False
)
```



<h3 id="pop"><code>pop</code></h3>

``` python
pop()
```

Removes the last layer in the model.

#### Raises:

* <b>`TypeError`</b>: if there are no layers in the model.

<h3 id="predict"><code>predict</code></h3>

``` python
predict(
    x,
    batch_size=32,
    verbose=0
)
```

Generates output predictions for the input samples.

The input samples are processed batch by batch.

#### Arguments:

* <b>`x`</b>: the input data, as a Numpy array.
* <b>`batch_size`</b>: integer.
* <b>`verbose`</b>: verbosity mode, 0 or 1.


#### Returns:

A Numpy array of predictions.

<h3 id="predict_classes"><code>predict_classes</code></h3>

``` python
predict_classes(
    x,
    batch_size=32,
    verbose=1
)
```

Generate class predictions for the input samples.

The input samples are processed batch by batch.

#### Arguments:

* <b>`x`</b>: input data, as a Numpy array or list of Numpy arrays
        (if the model has multiple inputs).
* <b>`batch_size`</b>: integer.
* <b>`verbose`</b>: verbosity mode, 0 or 1.


#### Returns:

A numpy array of class predictions.

<h3 id="predict_generator"><code>predict_generator</code></h3>

``` python
predict_generator(
    generator,
    steps,
    max_queue_size=10,
    workers=1,
    use_multiprocessing=False,
    verbose=0,
    **kwargs
)
```

Generates predictions for the input samples from a data generator.

The generator should return the same kind of data as accepted by
`predict_on_batch`.

#### Arguments:

* <b>`generator`</b>: generator yielding batches of input samples.
* <b>`steps`</b>: Total number of steps (batches of samples)
        to yield from `generator` before stopping.
* <b>`max_queue_size`</b>: maximum size for the generator queue
* <b>`workers`</b>: maximum number of processes to spin up
* <b>`use_multiprocessing`</b>: if True, use process based threading.
        Note that because this implementation
        relies on multiprocessing, you should not pass
        non picklable arguments to the generator
        as they can't be passed easily to children processes.
* <b>`verbose`</b>: verbosity mode, 0 or 1.
* <b>`**kwargs`</b>: support for legacy arguments.


#### Returns:

A Numpy array of predictions.


#### Raises:

* <b>`ValueError`</b>: In case the generator yields
        data in an invalid format.

<h3 id="predict_on_batch"><code>predict_on_batch</code></h3>

``` python
predict_on_batch(x)
```

Returns predictions for a single batch of samples.

#### Arguments:

* <b>`x`</b>: input data, as a Numpy array or list of Numpy arrays
        (if the model has multiple inputs).


#### Returns:

A Numpy array of predictions.

<h3 id="predict_proba"><code>predict_proba</code></h3>

``` python
predict_proba(
    x,
    batch_size=32,
    verbose=1
)
```

Generates class probability predictions for the input samples.

The input samples are processed batch by batch.

#### Arguments:

* <b>`x`</b>: input data, as a Numpy array or list of Numpy arrays
        (if the model has multiple inputs).
* <b>`batch_size`</b>: integer.
* <b>`verbose`</b>: verbosity mode, 0 or 1.


#### Returns:

A Numpy array of probability predictions.

<h3 id="reset_states"><code>reset_states</code></h3>

``` python
reset_states()
```



<h3 id="save"><code>save</code></h3>

``` python
save(
    filepath,
    overwrite=True,
    include_optimizer=True
)
```

Save the model to a single HDF5 file.

The savefile includes:
    - The model architecture, allowing to re-instantiate the model.
    - The model weights.
    - The state of the optimizer, allowing to resume training
        exactly where you left off.

This allows you to save the entirety of the state of a model
in a single file.

Saved models can be reinstantiated via `keras.models.load_model`.
The model returned by `load_model`
is a compiled model ready to be used (unless the saved model
was never compiled in the first place).

#### Arguments:

* <b>`filepath`</b>: String, path to the file to save the weights to.
* <b>`overwrite`</b>: Whether to silently overwrite any existing file at the
        target location, or provide the user with a manual prompt.
* <b>`include_optimizer`</b>: If True, save optimizer's state together.

Example:

```python
from keras.models import load_model

model.save('my_model.h5')  # creates a HDF5 file 'my_model.h5'
del model  # deletes the existing model

# returns a compiled model
# identical to the previous one
model = load_model('my_model.h5')
```

<h3 id="save_weights"><code>save_weights</code></h3>

``` python
save_weights(
    filepath,
    overwrite=True
)
```



<h3 id="set_weights"><code>set_weights</code></h3>

``` python
set_weights(weights)
```

Sets the weights of the model.

#### Arguments:

* <b>`weights`</b>: Should be a list
        of Numpy arrays with shapes and types matching
        the output of `model.get_weights()`.

<h3 id="summary"><code>summary</code></h3>

``` python
summary(
    line_length=None,
    positions=None,
    print_fn=None
)
```

Prints a string summary of the network.

#### Arguments:

* <b>`line_length`</b>: Total length of printed lines
        (e.g. set this to adapt the display to different
        terminal window sizes).
* <b>`positions`</b>: Relative or absolute positions of log elements
        in each line. If not provided,
        defaults to `[.33, .55, .67, 1.]`.
* <b>`print_fn`</b>: Print function to use. Defaults to `print`.
        It will be called on each line of the summary.
        You can set it to a custom function
        in order to capture the string summary.

<h3 id="test_on_batch"><code>test_on_batch</code></h3>

``` python
test_on_batch(
    x,
    y,
    sample_weight=None
)
```

Evaluates the model over a single batch of samples.

#### Arguments:

* <b>`x`</b>: input data, as a Numpy array or list of Numpy arrays
        (if the model has multiple inputs).
* <b>`y`</b>: labels, as a Numpy array.
* <b>`sample_weight`</b>: sample weights, as a Numpy array.


#### Returns:

Scalar test loss (if the model has no metrics)
or list of scalars (if the model computes other metrics).
The attribute `model.metrics_names` will give you
the display labels for the scalar outputs.


#### Raises:

* <b>`RuntimeError`</b>: if the model was never compiled.

<h3 id="to_json"><code>to_json</code></h3>

``` python
to_json(**kwargs)
```

Returns a JSON string containing the network configuration.

To load a network from a JSON save file, use
`keras.models.model_from_json(json_string, custom_objects={})`.

#### Arguments:

* <b>`**kwargs`</b>: Additional keyword arguments
        to be passed to `json.dumps()`.


#### Returns:

A JSON string.

<h3 id="to_yaml"><code>to_yaml</code></h3>

``` python
to_yaml(**kwargs)
```

Returns a yaml string containing the network configuration.

To load a network from a yaml save file, use
`keras.models.model_from_yaml(yaml_string, custom_objects={})`.

`custom_objects` should be a dictionary mapping
the names of custom losses / layers / etc to the corresponding
functions / classes.

#### Arguments:

* <b>`**kwargs`</b>: Additional keyword arguments
        to be passed to `yaml.dump()`.


#### Returns:

A YAML string.


#### Raises:

* <b>`ImportError`</b>: if yaml module is not found.

<h3 id="train_on_batch"><code>train_on_batch</code></h3>

``` python
train_on_batch(
    x,
    y,
    class_weight=None,
    sample_weight=None
)
```

Single gradient update over one batch of samples.

#### Arguments:

* <b>`x`</b>: input data, as a Numpy array or list of Numpy arrays
        (if the model has multiple inputs).
* <b>`y`</b>: labels, as a Numpy array.
* <b>`class_weight`</b>: dictionary mapping classes to a weight value,
        used for scaling the loss function (during training only).
* <b>`sample_weight`</b>: sample weights, as a Numpy array.


#### Returns:

Scalar training loss (if the model has no metrics)
or list of scalars (if the model computes other metrics).
The attribute `model.metrics_names` will give you
the display labels for the scalar outputs.


#### Raises:

* <b>`RuntimeError`</b>: if the model was never compiled.



