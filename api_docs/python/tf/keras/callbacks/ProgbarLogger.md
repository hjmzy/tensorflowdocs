<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.ProgbarLogger" />
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

# tf.keras.callbacks.ProgbarLogger

## Class `ProgbarLogger`

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)



Defined in [`tensorflow/python/keras/_impl/keras/callbacks.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/callbacks.py).

Callback that prints metrics to stdout.

#### Arguments:

* <b>`count_mode`</b>: One of "steps" or "samples".
        Whether the progress bar should
        count samples seens or steps (batches) seen.


#### Raises:

* <b>`ValueError`</b>: In case of invalid `count_mode`.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(count_mode='samples')
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





