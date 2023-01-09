MaxEnt
================
GW Dean
2023-01-06

Notes on Maximum Entropy. Adapted from McElreath-2019, Ch. 10

“The principle of maximum entropy applies this measure of uncertainty
\[Shannon’s\] to the problem of choosing among probability
distributions. Perhaps the simplest way to state the maximum entropy
principle is:

> The distribution that can happen the most ways is also the
> distribution with the biggest information entropy. The distribution
> with the biggest entropy is the most conservative distribution that
> obeys its constraints.

``` r
p <- list()
p$A <- c(0, 0, 10, 0, 0)
p$B <- c(0, 1, 8, 1, 0)
p$C <- c(0, 2, 6, 2, 0)
p$D <- c(1, 2, 4, 2, 1)
p$E <- c(2, 2, 2, 2, 2)

p_norm <- lapply(p, function(q) q / sum(q))

(H <- sapply(p_norm, function(q) -sum(ifelse(q==0, 0, q*log(q)))))
```

    ##         A         B         C         D         E 
    ## 0.0000000 0.6390319 0.9502705 1.4708085 1.6094379
