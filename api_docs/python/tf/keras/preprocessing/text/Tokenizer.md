<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.text.Tokenizer" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="fit_on_sequences"/>
<meta itemprop="property" content="fit_on_texts"/>
<meta itemprop="property" content="sequences_to_matrix"/>
<meta itemprop="property" content="texts_to_matrix"/>
<meta itemprop="property" content="texts_to_sequences"/>
<meta itemprop="property" content="texts_to_sequences_generator"/>
</div>

# tf.keras.preprocessing.text.Tokenizer

## Class `Tokenizer`





Defined in [`tensorflow/python/keras/_impl/keras/preprocessing/text.py`](https://www.tensorflow.org/code/tensorflow/python/keras/_impl/keras/preprocessing/text.py).

Text tokenization utility class.

This class allows to vectorize a text corpus, by turning each
text into either a sequence of integers (each integer being the index
of a token in a dictionary) or into a vector where the coefficient
for each token could be binary, based on word count, based on tf-idf...

#### Arguments:

* <b>`num_words`</b>: the maximum number of words to keep, based
        on word frequency. Only the most common `num_words` words will
        be kept.
* <b>`filters`</b>: a string where each element is a character that will be
        filtered from the texts. The default is all punctuation, plus
        tabs and line breaks, minus the `'` character.
* <b>`lower`</b>: boolean. Whether to convert the texts to lowercase.
* <b>`split`</b>: character or string to use for token splitting.
* <b>`char_level`</b>: if True, every character will be treated as a token.

By default, all punctuation is removed, turning the texts into
space-separated sequences of words
(words maybe include the `'` character). These sequences are then
split into lists of tokens. They will then be indexed or vectorized.

`0` is a reserved index that won't be assigned to any word.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    num_words=None,
    filters='!"#$%&()*+,-./:;<=>?@[\\]^_`{|}~\t\n',
    lower=True,
    split=' ',
    char_level=False
)
```



<h3 id="fit_on_sequences"><code>fit_on_sequences</code></h3>

``` python
fit_on_sequences(sequences)
```

Updates internal vocabulary based on a list of sequences.

Required before using `sequences_to_matrix`
(if `fit_on_texts` was never called).

#### Arguments:

* <b>`sequences`</b>: A list of sequence.
        A "sequence" is a list of integer word indices.

<h3 id="fit_on_texts"><code>fit_on_texts</code></h3>

``` python
fit_on_texts(texts)
```

Updates internal vocabulary based on a list of texts.

Required before using `texts_to_sequences` or `texts_to_matrix`.

#### Arguments:

* <b>`texts`</b>: can be a list of strings,
        or a generator of strings (for memory-efficiency)

<h3 id="sequences_to_matrix"><code>sequences_to_matrix</code></h3>

``` python
sequences_to_matrix(
    sequences,
    mode='binary'
)
```

Converts a list of sequences into a Numpy matrix.

#### Arguments:

* <b>`sequences`</b>: list of sequences
        (a sequence is a list of integer word indices).
* <b>`mode`</b>: one of "binary", "count", "tfidf", "freq"


#### Returns:

A Numpy matrix.


#### Raises:

* <b>`ValueError`</b>: In case of invalid `mode` argument,
        or if the Tokenizer requires to be fit to sample data.

<h3 id="texts_to_matrix"><code>texts_to_matrix</code></h3>

``` python
texts_to_matrix(
    texts,
    mode='binary'
)
```

Convert a list of texts to a Numpy matrix.

#### Arguments:

* <b>`texts`</b>: list of strings.
* <b>`mode`</b>: one of "binary", "count", "tfidf", "freq".


#### Returns:

A Numpy matrix.

<h3 id="texts_to_sequences"><code>texts_to_sequences</code></h3>

``` python
texts_to_sequences(texts)
```

Transforms each text in texts in a sequence of integers.

Only top "num_words" most frequent words will be taken into account.
Only words known by the tokenizer will be taken into account.

#### Arguments:

* <b>`texts`</b>: A list of texts (strings).


#### Returns:

A list of sequences.

<h3 id="texts_to_sequences_generator"><code>texts_to_sequences_generator</code></h3>

``` python
texts_to_sequences_generator(texts)
```

Transforms each text in texts in a sequence of integers.

Only top "num_words" most frequent words will be taken into account.
Only words known by the tokenizer will be taken into account.

#### Arguments:

* <b>`texts`</b>: A list of texts (strings).


#### Yields:

Yields individual sequences.



