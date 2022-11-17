
<!-- README.md is generated from README.Rmd. Please edit that file -->

# bis620.2022

<!-- badges: start -->

[![R-CMD-check](https://github.com/ahan98/bis620.2022/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/ahan98/bis620.2022/actions/workflows/R-CMD-check.yaml)
[![Test
coverage](https://github.com/ahan98/bis620.2022/actions/workflows/test-coverage.yaml/badge.svg)](https://github.com/ahan98/bis620.2022/actions/workflows/test-coverage.yaml)
[![lint](https://github.com/ahan98/bis620.2022/actions/workflows/lint.yaml/badge.svg)](https://github.com/ahan98/bis620.2022/actions/workflows/lint.yaml)
[![codecov](https://codecov.io/gh/ahan98/bis620.2022/branch/main/graph/badge.svg?token=XIPFAP6I5G)](https://codecov.io/gh/ahan98/bis620.2022)
<!-- badges: end -->

The `bis620.2022` package provides functionality for plotting and
transforming synthesized UKBiobank Accelerometry data.

## Installation

You can install the development version of bis620.2022 from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("ahan98/bis620.2022")
```

## Features

This package includes two main functions for interacting with the
data: - `R/plot.R/accel_plot()` plots acceleration in the 3 different
channels (X, Y, Z) as a time series. -
`R/spectral.R/spectral_signature()` calculates the spectral signature
for each channel by applying a Fourier transform.

## Example

``` r
## plot spectral signature for the first 100 samples of the acceleration data
library(bis620.2022)
data("ukb_accel")
samples_100 <- ukb_accel[1:100, ]
## calculate the (log) modulus of the Fourier coefficients of the signal
spectral <- spectral_signature(samples_100, take_log = TRUE)
## plot the signatures for each of the 3 channels
accel_plot(spectral)
```

<img src="man/figures/README-example-1.png" width="100%" />
