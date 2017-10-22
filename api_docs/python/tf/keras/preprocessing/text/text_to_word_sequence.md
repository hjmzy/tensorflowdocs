<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.text.text_to_word_sequence" />
</div>

# tf.keras.preprocessing.text.text_to_word_sequence

``` python
text_to_word_sequence(
    text,
    filters='!"#$%&()*+,-./:;<=>?@[\\]^_`{|}~\t\n',
    lower=True,
    split=' '
)
```



Defined in [`tensorflow/python/keras/_impl/keras/preprocessing/text.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/preprocessing/text.py).

Converts a text to a sequence of words (or tokens).

#### Arguments:

* <b>`text`</b>: Input text (string).
* <b>`filters`</b>: Sequence of characters to filter out.
* <b>`lower`</b>: Whether to convert the input to lowercase.
* <b>`split`</b>: Sentence split marker (string).


#### Returns:

A list of words (or tokens).