
<!-- README.md is generated from README.Rmd. Please edit that file -->

# SpaceX

<!-- badges: start -->
<!-- badges: end -->

The goal of SpaceX is to provide shared and cluster specfic gene
co-expression networks for spatial transcriptomics data.

## Installation

This package requires a Fortran compiler in order to work. Here are the
instructions:

-   Windows: install the Rtools package that is appropriate for your
    version of R

-   Mac: Go to this website and follow the instructions:
    (<https://mac.R-project.org/tools/>)

-   Linux: From a terminal, do the following: `sudo apt install gcc`.
    That will bring in multiple compilers.

The package requires a dependency that is not available on CRAN. Install
it with:

``` r
remotes::install_github("rdevito/MSFA")
```

You can install the released version of SpaceX from
(<https://github.com/SatwikAch/SpaceX>) with:

``` r
devtools::install_github("SatwikAch/SpaceX")
```

``` r
library(SpaceX)
#> Loading required package: PQLseq
```

``` r
## Reading the Breast cancer data

## Spatial locations
head(BC_loc)

## Gene expression for data
head(BC_count) 

## Data processing
G <-dim(BC_count)[2] ## number of genes
N <-dim(BC_count)[1] ## number of locations

## Application to SpaceX algorithm
BC_fit <- SpaceX(BC_count,BC_loc[,1:2],BC_loc[,3],sPMM=FALSE,Post_process = TRUE,numCore = 2)

## Shared_network :: Shared co-expression matrix
## Cluster_network :: Cluster specific co-expression matrices
```

You can view the supplementary file at this link:
<https://bookdown.org/satwik91/SpaceX_supplementary/>.

Tutorial website can be found here: https://satwikach.github.io/SpaceX.github.io/

