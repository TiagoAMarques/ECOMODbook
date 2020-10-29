
# Introduction {#intro}

This is being written as a bookdown project. Maybe one day it will become a book, for now, these are notes I am using for my course on "Modelação Ecológica" at FCUL.

## What is a regression?

Where does the word come from? Gauss and regression towards the mean.

A regression is a model that allows us to predict a response variable $y$ (a.k.a the dependent variable, because it depends on the other variables) as a function of the values of covariates (a.k.a. predictors, explanatory or independent variables).

## The general linear model

A general expression for a regression model (i.e. the expression for a generalized linear model is)

$$ f[E(Y|X)] = \mu = \beta_0+\beta_1 x_1 + ... + \beta_k x_k $$
where $f$ is a function - also known as the **link function** - that links the mean value of the response, conditional on the value of the predictors, to the **linear predictor** $\beta_0+\beta_1 x_1 + ... + \beta_k x_k$ ($\mu$, a linear function of $k$ covariates). In general books tend to represent this as

$$ E(Y|X) =  f^{-1}(\beta_0+\beta_1 x_1 + ... + \beta_k x_k) $$
i.e., where what is shown is the inverse of the link function, 
and sometimes the notation ignores the formal conditioning on the values of the covariates

$$ E(Y) =  f^{-1}(\beta_0+\beta_1 x_1 + ... + \beta_k x_k) $$


Because this is a model, for any given observation we have 

$$ f{(y_i|x_i)} =  \beta_0+\beta_1 x_{1i} + ... + \beta_k x_{ki} + e_i $$

where the $e_i$ represents the residual (a.k.a. the error). 

Most people are used to see the representation when the link function is the identity and hence

$$ y_i =  \beta_0+\beta_1 x_{1i} + ... + \beta_k x_{ki} + e_i $$

The simplest form of a generalized linear model is that where there is only one predictor, the link function is the identity and the error is Gaussian (or normal). Note that is the usual simple linear regression model 

$$y_i=a+bx_i+e_i$$
with residuals

$$e_i=y_i - (a+bx_i)= y_i-\hat y_i$$

being Gaussian, i.e. $e_i$~Gau(0,$\sigma$), and where the link function is the identity (i.e. $f(E(y))=1 \times E(y)=E(y)$).

## Bookdown template leftovers

You can label chapter and section titles using `{#label}` after them, e.g., we can reference Chapter <a href="#intro">2</a>. If you do not manually label them, there will be automatic labels anyway, e.g., Chapter <a href="#methods"><strong>??</strong></a>.

Figures and tables with captions will be placed in `figure` and `table` environments, respectively.


```r
par(mar = c(4, 4, .1, .1))
plot(pressure, type = 'b', pch = 19)
```

<div class="figure" style="text-align: center">
<img src="ECOMODbook_files/figure-epub3/nice-fig-1.png" alt="Here is a nice figure!" width="80%" />
<p class="caption">Figure 2.1: Here is a nice figure!</p>
</div>

Reference a figure by its code chunk label with the `fig:` prefix, e.g., see Figure <a href="#fig:nice-fig">2.1</a>. Similarly, you can reference tables generated from `knitr::kable()`, e.g., see Table <a href="#tab:nice-tab">2.1</a>.


```r
knitr::kable(
  head(iris, 20), caption = 'Here is a nice table!',
  booktabs = TRUE
)
```



Table: Table 2.1: Here is a nice table!

| Sepal.Length| Sepal.Width| Petal.Length| Petal.Width|Species |
|------------:|-----------:|------------:|-----------:|:-------|
|          5.1|         3.5|          1.4|         0.2|setosa  |
|          4.9|         3.0|          1.4|         0.2|setosa  |
|          4.7|         3.2|          1.3|         0.2|setosa  |
|          4.6|         3.1|          1.5|         0.2|setosa  |
|          5.0|         3.6|          1.4|         0.2|setosa  |
|          5.4|         3.9|          1.7|         0.4|setosa  |
|          4.6|         3.4|          1.4|         0.3|setosa  |
|          5.0|         3.4|          1.5|         0.2|setosa  |
|          4.4|         2.9|          1.4|         0.2|setosa  |
|          4.9|         3.1|          1.5|         0.1|setosa  |
|          5.4|         3.7|          1.5|         0.2|setosa  |
|          4.8|         3.4|          1.6|         0.2|setosa  |
|          4.8|         3.0|          1.4|         0.1|setosa  |
|          4.3|         3.0|          1.1|         0.1|setosa  |
|          5.8|         4.0|          1.2|         0.2|setosa  |
|          5.7|         4.4|          1.5|         0.4|setosa  |
|          5.4|         3.9|          1.3|         0.4|setosa  |
|          5.1|         3.5|          1.4|         0.3|setosa  |
|          5.7|         3.8|          1.7|         0.3|setosa  |
|          5.1|         3.8|          1.5|         0.3|setosa  |

You can write citations, too. For example, we are using the **bookdown** package [@R-bookdown] in this sample book, which was built on top of R Markdown and **knitr** [@xie2015].

<!--chapter:end:01-intro.Rmd-->
