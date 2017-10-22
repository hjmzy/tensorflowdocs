<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.ImageDataGenerator" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="fit"/>
<meta itemprop="property" content="flow"/>
<meta itemprop="property" content="flow_from_directory"/>
<meta itemprop="property" content="random_transform"/>
<meta itemprop="property" content="standardize"/>
</div>

# tf.keras.preprocessing.image.ImageDataGenerator

## Class `ImageDataGenerator`





Defined in [`tensorflow/python/keras/_impl/keras/preprocessing/image.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/preprocessing/image.py).

Generate minibatches of image data with real-time data augmentation.

#### Arguments:

* <b>`featurewise_center`</b>: set input mean to 0 over the dataset.
* <b>`samplewise_center`</b>: set each sample mean to 0.
* <b>`featurewise_std_normalization`</b>: divide inputs by std of the dataset.
* <b>`samplewise_std_normalization`</b>: divide each input by its std.
* <b>`zca_whitening`</b>: apply ZCA whitening.
* <b>`zca_epsilon`</b>: epsilon for ZCA whitening. Default is 1e-6.
* <b>`rotation_range`</b>: degrees (0 to 180).
* <b>`width_shift_range`</b>: fraction of total width.
* <b>`height_shift_range`</b>: fraction of total height.
* <b>`shear_range`</b>: shear intensity (shear angle in radians).
* <b>`zoom_range`</b>: amount of zoom. if scalar z, zoom will be randomly picked
        in the range [1-z, 1+z]. A sequence of two can be passed instead
        to select this range.
* <b>`channel_shift_range`</b>: shift range for each channels.
* <b>`fill_mode`</b>: points outside the boundaries are filled according to the
        given mode ('constant', 'nearest', 'reflect' or 'wrap'). Default
        is 'nearest'.
* <b>`cval`</b>: value used for points outside the boundaries when fill_mode is
        'constant'. Default is 0.
* <b>`horizontal_flip`</b>: whether to randomly flip images horizontally.
* <b>`vertical_flip`</b>: whether to randomly flip images vertically.
* <b>`rescale`</b>: rescaling factor. If None or 0, no rescaling is applied,
        otherwise we multiply the data by the value provided. This is
        applied after the `preprocessing_function` (if any provided)
        but before any other transformation.
* <b>`preprocessing_function`</b>: function that will be implied on each input.
        The function will run before any other modification on it.
        The function should take one argument:
        one image (Numpy tensor with rank 3),
        and should output a Numpy tensor with the same shape.
* <b>`data_format`</b>: 'channels_first' or 'channels_last'. In 'channels_first'
      mode, the channels dimension
        (the depth) is at index 1, in 'channels_last' mode it is at index 3.
        It defaults to the `image_data_format` value found in your
        Keras config file at `~/.keras/keras.json`.
        If you never set it, then it will be "channels_last".

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    featurewise_center=False,
    samplewise_center=False,
    featurewise_std_normalization=False,
    samplewise_std_normalization=False,
    zca_whitening=False,
    zca_epsilon=1e-06,
    rotation_range=0.0,
    width_shift_range=0.0,
    height_shift_range=0.0,
    shear_range=0.0,
    zoom_range=0.0,
    channel_shift_range=0.0,
    fill_mode='nearest',
    cval=0.0,
    horizontal_flip=False,
    vertical_flip=False,
    rescale=None,
    preprocessing_function=None,
    data_format=None
)
```



<h3 id="fit"><code>fit</code></h3>

``` python
fit(
    x,
    augment=False,
    rounds=1,
    seed=None
)
```

Fits internal statistics to some sample data.

Required for featurewise_center, featurewise_std_normalization
and zca_whitening.

#### Arguments:

* <b>`x`</b>: Numpy array, the data to fit on. Should have rank 4.
        In case of grayscale data,
        the channels axis should have value 1, and in case
        of RGB data, it should have value 3.
* <b>`augment`</b>: Whether to fit on randomly augmented samples
* <b>`rounds`</b>: If `augment`,
        how many augmentation passes to do over the data
* <b>`seed`</b>: random seed.


#### Raises:

* <b>`ValueError`</b>: in case of invalid input `x`.
* <b>`ImportError`</b>: if Scipy is not available.

<h3 id="flow"><code>flow</code></h3>

``` python
flow(
    x,
    y=None,
    batch_size=32,
    shuffle=True,
    seed=None,
    save_to_dir=None,
    save_prefix='',
    save_format='png'
)
```



<h3 id="flow_from_directory"><code>flow_from_directory</code></h3>

``` python
flow_from_directory(
    directory,
    target_size=(256, 256),
    color_mode='rgb',
    classes=None,
    class_mode='categorical',
    batch_size=32,
    shuffle=True,
    seed=None,
    save_to_dir=None,
    save_prefix='',
    save_format='png',
    follow_links=False
)
```



<h3 id="random_transform"><code>random_transform</code></h3>

``` python
random_transform(
    x,
    seed=None
)
```

Randomly augment a single image tensor.

#### Arguments:

* <b>`x`</b>: 3D tensor, single image.
* <b>`seed`</b>: random seed.


#### Returns:

A randomly transformed version of the input (same shape).


#### Raises:

* <b>`ImportError`</b>: if Scipy is not available.

<h3 id="standardize"><code>standardize</code></h3>

``` python
standardize(x)
```

Apply the normalization configuration to a batch of inputs.

#### Arguments:

* <b>`x`</b>: batch of inputs to be normalized.


#### Returns:

The inputs, normalized.



