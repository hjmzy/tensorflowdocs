<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.eval" />
<meta itemprop="property" content="INCEPTION_DEFAULT_IMAGE_SIZE"/>
<meta itemprop="property" content="frechet_inception_distance"/>
<meta itemprop="property" content="inception_score"/>
</div>

# Module: tf.contrib.gan.eval



Defined in [`tensorflow/contrib/gan/python/eval/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/eval/__init__.py).

TFGAN grouped API. Please see README.md for details and usage.

## Modules

[`classifier_metrics`](../../../tf/contrib/gan/eval/classifier_metrics.md) module: Model evaluation tools for TFGAN.

[`eval_utils`](../../../tf/contrib/gan/eval/eval_utils.md) module: Utility file for visualizing generated images.

[`summaries`](../../../tf/contrib/gan/eval/summaries.md) module: Common TFGAN summaries.

## Functions

[`add_gan_model_image_summaries(...)`](../../../tf/contrib/gan/eval/add_gan_model_image_summaries.md): Adds image summaries for real and fake images.

[`add_gan_model_summaries(...)`](../../../tf/contrib/gan/eval/add_gan_model_summaries.md): Adds typical GANModel summaries.

[`add_image_comparison_summaries(...)`](../../../tf/contrib/gan/eval/add_image_comparison_summaries.md): Adds image summaries to compare triplets of images.

[`add_regularization_loss_summaries(...)`](../../../tf/contrib/gan/eval/add_regularization_loss_summaries.md): Adds summaries for a regularization losses..

[`classifier_score(...)`](../../../tf/contrib/gan/eval/classifier_score.md): Classifier score for evaluating a conditional generative model.

[`frechet_classifier_distance(...)`](../../../tf/contrib/gan/eval/frechet_classifier_distance.md): Classifier distance for evaluating a generative model.

[`get_graph_def_from_disk(...)`](../../../tf/contrib/gan/eval/get_graph_def_from_disk.md): Get a GraphDef proto from a disk location.

[`get_graph_def_from_resource(...)`](../../../tf/contrib/gan/eval/get_graph_def_from_resource.md): Get a GraphDef proto from within a .par file.

[`get_graph_def_from_url_tarball(...)`](../../../tf/contrib/gan/eval/get_graph_def_from_url_tarball.md): Get a GraphDef proto from a tarball on the web.

[`image_grid(...)`](../../../tf/contrib/gan/eval/image_grid.md): Arrange a minibatch of images into a grid to form a single image.

[`image_reshaper(...)`](../../../tf/contrib/gan/eval/image_reshaper.md): A reshaped summary image.

[`preprocess_image(...)`](../../../tf/contrib/gan/eval/preprocess_image.md): Prepare a batch of images for evaluation.

[`run_image_classifier(...)`](../../../tf/contrib/gan/eval/run_image_classifier.md): Runs a network from a frozen graph.

[`run_inception(...)`](../../../tf/contrib/gan/eval/run_inception.md): Run images through a pretrained Inception classifier.

## Other Members

`INCEPTION_DEFAULT_IMAGE_SIZE`

`frechet_inception_distance`

`inception_score`

