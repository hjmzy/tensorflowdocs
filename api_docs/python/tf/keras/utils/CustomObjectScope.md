<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.utils.CustomObjectScope" />
<meta itemprop="property" content="__enter__"/>
<meta itemprop="property" content="__exit__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.keras.utils.CustomObjectScope

## Class `CustomObjectScope`





Defined in [`tensorflow/python/keras/_impl/keras/utils/generic_utils.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/utils/generic_utils.py).

Provides a scope that changes to `_GLOBAL_CUSTOM_OBJECTS` cannot escape.

Code within a `with` statement will be able to access custom objects
by name. Changes to global custom objects persist
within the enclosing `with` statement. At end of the `with` statement,
global custom objects are reverted to state
at beginning of the `with` statement.

Example:

Consider a custom object `MyObject`

```python
    with CustomObjectScope({'MyObject':MyObject}):
        layer = Dense(..., kernel_regularizer='MyObject')
        # save, load, etc. will recognize custom object by name
```

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(*args)
```



<h3 id="__enter__"><code>__enter__</code></h3>

``` python
__enter__()
```



<h3 id="__exit__"><code>__exit__</code></h3>

``` python
__exit__(
    *args,
    **kwargs
)
```





