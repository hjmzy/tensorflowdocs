<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.loss_functions.NormalMeanNegativeLogProbLoss" />
<meta itemprop="property" content="fisher_factor_inner_shape"/>
<meta itemprop="property" content="fisher_factor_inner_static_shape"/>
<meta itemprop="property" content="hessian_factor_inner_shape"/>
<meta itemprop="property" content="hessian_factor_inner_static_shape"/>
<meta itemprop="property" content="inputs"/>
<meta itemprop="property" content="params"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="evaluate"/>
<meta itemprop="property" content="evaluate_on_sample"/>
<meta itemprop="property" content="multiply_fisher"/>
<meta itemprop="property" content="multiply_fisher_factor"/>
<meta itemprop="property" content="multiply_fisher_factor_replicated_one_hot"/>
<meta itemprop="property" content="multiply_fisher_factor_transpose"/>
<meta itemprop="property" content="multiply_hessian"/>
<meta itemprop="property" content="multiply_hessian_factor"/>
<meta itemprop="property" content="multiply_hessian_factor_replicated_one_hot"/>
<meta itemprop="property" content="multiply_hessian_factor_transpose"/>
<meta itemprop="property" content="sample"/>
</div>

# tf.contrib.kfac.loss_functions.NormalMeanNegativeLogProbLoss

## Class `NormalMeanNegativeLogProbLoss`

Inherits From: [`DistributionNegativeLogProbLoss`](../../../../tf/contrib/kfac/loss_functions/DistributionNegativeLogProbLoss.md), [`NaturalParamsNegativeLogProbLoss`](../../../../tf/contrib/kfac/loss_functions/NaturalParamsNegativeLogProbLoss.md)



Defined in [`tensorflow/contrib/kfac/python/ops/loss_functions.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/loss_functions.py).

Neg log prob loss for a normal distribution parameterized by a mean vector.


Note that the covariance is treated as a constant 'var' times the identity.
Also note that the Fisher for such a normal distribution with respect the mean
parameter is given by:

   F = (1/var) * I

See for example https://www.ii.pwr.edu.pl/~tomczak/PDF/[JMT]Fisher_inf.pdf.

## Properties

<h3 id="fisher_factor_inner_shape"><code>fisher_factor_inner_shape</code></h3>



<h3 id="fisher_factor_inner_static_shape"><code>fisher_factor_inner_static_shape</code></h3>



<h3 id="hessian_factor_inner_shape"><code>hessian_factor_inner_shape</code></h3>



<h3 id="hessian_factor_inner_static_shape"><code>hessian_factor_inner_static_shape</code></h3>



<h3 id="inputs"><code>inputs</code></h3>



<h3 id="params"><code>params</code></h3>





## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    mean,
    var=0.5,
    targets=None,
    seed=None
)
```



<h3 id="evaluate"><code>evaluate</code></h3>

``` python
evaluate()
```

Evaluate the loss function.

<h3 id="evaluate_on_sample"><code>evaluate_on_sample</code></h3>

``` python
evaluate_on_sample(seed=None)
```



<h3 id="multiply_fisher"><code>multiply_fisher</code></h3>

``` python
multiply_fisher(vector)
```



<h3 id="multiply_fisher_factor"><code>multiply_fisher_factor</code></h3>

``` python
multiply_fisher_factor(vector)
```



<h3 id="multiply_fisher_factor_replicated_one_hot"><code>multiply_fisher_factor_replicated_one_hot</code></h3>

``` python
multiply_fisher_factor_replicated_one_hot(index)
```



<h3 id="multiply_fisher_factor_transpose"><code>multiply_fisher_factor_transpose</code></h3>

``` python
multiply_fisher_factor_transpose(vector)
```



<h3 id="multiply_hessian"><code>multiply_hessian</code></h3>

``` python
multiply_hessian(vector)
```



<h3 id="multiply_hessian_factor"><code>multiply_hessian_factor</code></h3>

``` python
multiply_hessian_factor(vector)
```



<h3 id="multiply_hessian_factor_replicated_one_hot"><code>multiply_hessian_factor_replicated_one_hot</code></h3>

``` python
multiply_hessian_factor_replicated_one_hot(index)
```



<h3 id="multiply_hessian_factor_transpose"><code>multiply_hessian_factor_transpose</code></h3>

``` python
multiply_hessian_factor_transpose(vector)
```



<h3 id="sample"><code>sample</code></h3>

``` python
sample(seed)
```





