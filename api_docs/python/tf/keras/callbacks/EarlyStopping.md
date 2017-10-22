<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.EarlyStopping" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="on_batch_begin"/>
<meta itemprop="property" content="on_batch_end"/>
<meta itemprop="property" content="on_epoch_begin"/>
<meta itemprop="property" content="on_epoch_end"/>
<meta itemprop="property" content="on_train_begin"/>
<meta itemprop="property" content="on_train_end"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.EarlyStopping

## Class `EarlyStopping`

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)



Defined in [`tensorflow/python/keras/_impl/keras/callbacks.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/callbacks.py).

Stop training when a monitored quantity has stopped improving.

#### Arguments:

* <b>`monitor`</b>: quantity to be monitored.
* <b>`min_delta`</b>: minimum change in the monitored quantity
        to qualify as an improvement, i.e. an absolute
        change of less than min_delta, will count as no
        improvement.
* <b>`patience`</b>: number of epochs with no improvement
        after which training will be stopped.
* <b>`verbose`</b>: verbosity mode.
* <b>`mode`</b>: one of {auto, min, max}. In `min` mode,
        training will stop when the quantity
        monitored has stopped decreasing; in `max`
        mode it will stop when the quantity
        monitored has stopped increasing; in `auto`
        mode, the direction is automatically inferred
        from the name of the monitored quantity.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    monitor='val_loss',
    min_delta=0,
    patience=0,
    verbose=0,
    mode='auto'
)
```



<h3 id="on_batch_begin"><code>on_batch_begin</code></h3>

``` python
on_batch_begin(
    batch,
    logs=None
)
```



<h3 id="on_batch_end"><code>on_batch_end</code></h3>

``` python
on_batch_end(
    batch,
    logs=None
)
```



<h3 id="on_epoch_begin"><code>on_epoch_begin</code></h3>

``` python
on_epoch_begin(
    epoch,
    logs=None
)
```



<h3 id="on_epoch_end"><code>on_epoch_end</code></h3>

``` python
on_epoch_end(
    epoch,
    logs=None
)
```



<h3 id="on_train_begin"><code>on_train_begin</code></h3>

``` python
on_train_begin(logs=None)
```



<h3 id="on_train_end"><code>on_train_end</code></h3>

``` python
on_train_end(logs=None)
```



<h3 id="set_model"><code>set_model</code></h3>

``` python
set_model(model)
```



<h3 id="set_params"><code>set_params</code></h3>

``` python
set_params(params)
```





