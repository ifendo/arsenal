
# The `arsenal` Package <img src="man/figures/arsenal.png" alt="Arsenal logo" style="float:right;height:232.25px" align="right" height="232.25">

[![CRAN_Status_Badge](http://www.r-pkg.org/badges/version/arsenal)](https://CRAN.R-project.org/package=arsenal)
[![Total Downloads](http://cranlogs.r-pkg.org/badges/grand-total/arsenal)](https://CRAN.R-project.org/package=arsenal)
[![Downloads](http://cranlogs.r-pkg.org/badges/arsenal)](https://CRAN.R-project.org/package=arsenal)
[![Travis-CI Build Status](https://travis-ci.org/eheinzen/arsenal.svg?branch=master)](https://travis-ci.org/eheinzen/arsenal)

## Overview

The goal of `library(arsenal)` is to make statistical reporting easy. It includes many functions which the useR will find useful to have
in his/her "arsenal" of functions. There are, at this time, 6 main functions, documented below. Each of these functions is
motivated by a local SAS macro or procedure of similar functionality.

Note that `arsenal` v2.0.0 may not be backwards compatible with previous versions.
See the `NEWS` file for more details.

## The `tableby()` Function

`tableby()` is a function to easily summarize a set of independent variables by one or more categorical variables.
Optionally, an appropriate test is performed to test the distribution of the independent variables across
the levels of the categorical variable. Options for this function are easily controlled using `tableby.control()`.

The `tableby()` output is easily knitted in an Rmarkdown document or displayed in the command line using the `summary()` function.
Other S3 methods are implemented for objects from `tableby()`, including `print()`, `[`, `as.data.frame()`, and `merge()`.

## The `paired()` Function

`paired()` is a function to easily summarize a set of independent variables across two time points.
Optionally, an appropriate test is performed to test the distribution of the independent variables across
the time points. Options for this function are easily controlled using `paired.control()`.

The `paired()` output is easily knitted in an Rmarkdown document or displayed in the command line using the `summary()` function.
It has the same S3 methods as `tableby()`, since it's a special case of the `tableby()` object.

## The `modelsum()` Function

`modelsum()` is a function to fit and summarize models for each independent variable with one or more response variables,
with options to adjust for covariates for each model. Options for this function are easily controlled using `modelsum.control()`.

The `modelsum` output is easily knitted in an Rmarkdown document or displayed in the command line using the `summary()` function.
Other S3 methods are implemented for objects from `modelsum()`, including `print()`, `[`, `as.data.frame()`, and `merge()`.

## The `freqlist()` Function

`freqlist()` is a function to approximate the output from SAS's `PROC FREQ` procedure when using the `/list` option of the `TABLE` statement.
Options for this function are easily controlled using `freq.control()`.

The `freqlist()` output is easily knitted in an Rmarkdown document or displayed in the command line using the `summary()` function.
Other S3 methods are implemented for objects from `freqlist()`, including `print()`, `[`, `as.data.frame()`, and `merge()`.

## The `compare.data.frame()` Function

`compare.data.frame()` is the S3 method for comparing two data.frames and reporting any differences between them,
much like SAS's `PROC COMPARE` procedure.

The `compare.data.frame()` output is easily knitted in an Rmarkdown document or displayed in the command line using the `summary()` function.
Other S3 methods are implemented for objects of class `"compare.data.frame"`, including `print()` and `diffs()`.

## The `write2*()` Family of Functions

`write2word()`, `write2pdf()`, and `write2html()` are functions to output a table into a document, much like SAS's `ODS` procedure.
  The S3 method behind them is `write2()`. There are methods implemented for `tableby()`, `modelsum()`, `freqlist()`, and `compare()`, and
  also methods for `knitr::kable()`, `xtable::xtable()`, and `pander::pander_return()`. Another option is to coerce an object using
  `verbatim()` to print out the results monospaced (as if they were in the terminal)--the default method does this automatically.
  To output multiple tables into a document, simply make a list of them and call the same function as before. A YAML
  header can be added using `yaml()`. Code chunks can be written using `code.chunk()`.
  
  For more information, see `vignette("write2")`.

## Other Notable Functions

* `keep.labels()` keeps the `'label'` attribute on an R object when subsetting.

* `formulize()` is a shortcut to collapse variable names into a formula.

* `mdy.Date()` and `Date.mdy()` convert numeric dates for month, day, and year to Date object, and vice versa.

* `is.Date`: tests if an object is a date.

* `%nin%` tests for "not in", the negation of `%in%`.

* `allNA()` tests for all elements being NA, and `includeNA()` makes NAs explicit values.
