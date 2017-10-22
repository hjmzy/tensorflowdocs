<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.eval.add_gan_model_image_summaries" />
</div>

# tf.contrib.gan.eval.add_gan_model_image_summaries

### Aliases:

* `tf.contrib.gan.eval.add_gan_model_image_summaries`
* `tf.contrib.gan.eval.summaries.add_gan_model_image_summaries`

``` python
add_gan_model_image_summaries(
    gan_model,
    grid_size=4
)
```



Defined in [`tensorflow/contrib/gan/python/eval/python/summaries_impl.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/eval/python/summaries_impl.py).

Adds image summaries for real and fake images.

#### Args:

* <b>`gan_model`</b>: A GANModel tuple.
* <b>`grid_size`</b>: The size of an image grid.


#### Raises:

* <b>`ValueError`</b>: If real and generated data aren't images.