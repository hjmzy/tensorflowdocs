<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.Iterator" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="__next__"/>
<meta itemprop="property" content="reset"/>
</div>

# tf.keras.preprocessing.image.Iterator

## Class `Iterator`





Defined in [`tensorflow/python/keras/_impl/keras/preprocessing/image.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/preprocessing/image.py).

Abstract base class for image data iterators.

#### Arguments:

* <b>`n`</b>: Integer, total number of samples in the dataset to loop over.
* <b>`batch_size`</b>: Integer, size of a batch.
* <b>`shuffle`</b>: Boolean, whether to shuffle the data between epochs.
* <b>`seed`</b>: Random seeding for data shuffling.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    n,
    batch_size,
    shuffle,
    seed
)
```



<h3 id="__iter__"><code>__iter__</code></h3>

``` python
__iter__()
```



<h3 id="__next__"><code>__next__</code></h3>

``` python
__next__(
    *args,
    **kwargs
)
```



<h3 id="reset"><code>reset</code></h3>

``` python
reset()
```





