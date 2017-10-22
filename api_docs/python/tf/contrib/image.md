<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.image" />
</div>

# Module: tf.contrib.image



Defined in [`tensorflow/contrib/image/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/image/__init__.py).

Ops for image manipulation.

### API

This module provides functions for image manipulation; currently, chrominance
transformas (including changing saturation and hue) in YIQ space and
projective transforms (including rotation) are supported.


## Functions

[`angles_to_projective_transforms(...)`](../../tf/contrib/image/angles_to_projective_transforms.md): Returns projective transform(s) for the given angle(s).

[`compose_transforms(...)`](../../tf/contrib/image/compose_transforms.md): Composes the transforms tensors.

[`rotate(...)`](../../tf/contrib/image/rotate.md): Rotate image(s) by the passed angle(s) in radians.

[`single_image_random_dot_stereograms(...)`](../../tf/contrib/image/single_image_random_dot_stereograms.md): Output a RandomDotStereogram Tensor for export via encode_PNG/JPG OP.

[`transform(...)`](../../tf/contrib/image/transform.md): Applies the given transform(s) to the image(s).

[`translate(...)`](../../tf/contrib/image/translate.md): Translate image(s) by the passed vectors(s).

[`translations_to_projective_transforms(...)`](../../tf/contrib/image/translations_to_projective_transforms.md): Returns projective transform(s) for the given translation(s).

