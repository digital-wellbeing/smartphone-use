# (PART) Study 1 {-}

# Setting up

In this section, I process and analyze the data for Study 1.
First, I load all libraries that we need for the analysis.
The `pacman` package just makes it easier to load packages.
Note that the final version of this page doesn't evaluate the code chunk below to avoid installing packages on your machine.
If you're fine with them being installed, set `eval = TRUE`.


```r
if (!requireNamespace("pacman"))
  install.packages("pacman")

library(pacman)

# load packages
p_load(
  tidyverse,
  here
)

# set seed
set.seed(42)
```
