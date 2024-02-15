# Play with Quarto v. 1.4
Charalampos A. Lazaris
2024-02-15

- [Introduction](#introduction)
- [Code](#code)

# Introduction

This is a Quarto tutorial based on the official Posit cheatsheet. It
features some of the new features in Quarto v. 1.4.

# Code

Let’s insert some inline code in R: 2 gives 2

Here is some `R` code:

<details open class="code-fold">
<summary>Code</summary>

``` r
p <- 1 + 1
print(p)
```

</details>

    [1] 2

Now, let’s import some data and create a graph, after loading the
required libraries:

<details open class="code-fold">
<summary>Code</summary>

``` r
library(tidyverse)
```

</details>
<details open class="code-fold">
<summary>Code</summary>

``` r
data(iris)
glimpse(iris)
```

</details>

    Rows: 150
    Columns: 5
    $ Sepal.Length <dbl> 5.1, 4.9, 4.7, 4.6, 5.0, 5.4, 4.6, 5.0, 4.4, 4.9, 5.4, 4.…
    $ Sepal.Width  <dbl> 3.5, 3.0, 3.2, 3.1, 3.6, 3.9, 3.4, 3.4, 2.9, 3.1, 3.7, 3.…
    $ Petal.Length <dbl> 1.4, 1.4, 1.3, 1.5, 1.4, 1.7, 1.4, 1.5, 1.4, 1.5, 1.5, 1.…
    $ Petal.Width  <dbl> 0.2, 0.2, 0.2, 0.2, 0.2, 0.4, 0.3, 0.2, 0.2, 0.1, 0.2, 0.…
    $ Species      <fct> setosa, setosa, setosa, setosa, setosa, setosa, setosa, s…

We now plot `Petal.Length` vs. `Petal.Width`:

<details open class="code-fold">
<summary>Code</summary>

``` r
ggplot(data = iris, aes(x = Petal.Width, y = Petal.Length)) +
    geom_point() +
    geom_smooth(method = "lm", se = TRUE) +
    ggtitle("Petal length vs. petal width") +
    xlab("Petal width") + ylab("Petal length") +
    theme_bw()
```

</details>

    `geom_smooth()` using formula = 'y ~ x'

<img
src="Play_with_Quarto_files/figure-commonmark/unnamed-chunk-4-1.png"
data-fig-align="center" />

> [!TIP]
>
> ### Consistency
>
> Use `dplyr` for data wrangling and `ggplot2` for plotting - keep it
> consistent
