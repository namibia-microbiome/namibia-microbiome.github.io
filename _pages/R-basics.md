---
title: "R basics"
excerpt: "A short introduction to the essential tools and commands used in R."
permalink: /materials/r-basics/
layout: single
---

This tutorial introduces the core R skills needed for the workshop. Work
through the examples in an R script so that your analysis can be saved and run
again.

## Learning outcomes

By the end of this tutorial, you should be able to:

- use the R console and an R script;
- create objects, vectors and data frames;
- inspect and select data;
- import a CSV file; and
- recognise and handle missing values.

## 1. The console and scripts

The **console** runs one command at a time. A **script** is a text file ending
in `.R` that keeps a reusable record of your commands. Write your analysis in a
script and use the console to test short commands.

```r
# Lines beginning with # are comments
2 + 3
sqrt(16)
```

## 2. Objects and vectors

Use `<-` to assign a value to an object. A vector stores several values of the
same basic type.

```r
site_name <- "Windhoek"
sample_count <- 12

ph <- c(6.2, 6.8, 7.1, 6.5)
mean(ph)
length(ph)
```

R is case-sensitive, so `ph`, `Ph` and `PH` are different names.

## 3. Data frames

A data frame stores observations in rows and variables in columns.

```r
samples <- data.frame(
  sample_id = c("S1", "S2", "S3", "S4"),
  treatment = c("control", "control", "biofertiliser", "biofertiliser"),
  ph = c(6.2, 6.8, 7.1, 6.5)
)

head(samples)
str(samples)
summary(samples)
```

Use `$` to select one column and square brackets to select rows or columns.

```r
samples$ph
samples[1, ]
samples[, c("sample_id", "ph")]
samples[samples$ph > 6.5, ]
```

## 4. Importing data

Keep the original data file unchanged and perform any cleaning in your script.
If a CSV file is in the working directory, import it with:

```r
samples <- read.csv("samples.csv")

head(samples)
dim(samples)
names(samples)
str(samples)
```

Always inspect a dataset after importing it. Check that numbers, text and
categories have been interpreted correctly.

## 5. Missing values

R represents a missing value as `NA`. A missing observation is not necessarily
the same as a measured zero.

```r
ph <- c(6.2, NA, 7.1, 6.5)

is.na(ph)
sum(is.na(ph))
mean(ph, na.rm = TRUE)
```

Only remove or replace missing values when there is a clear scientific reason,
and record that decision in your script.

## 6. A first plot

Base R can produce a quick plot without loading an additional package.

```r
plot(
  samples$ph,
  xlab = "Sample number",
  ylab = "Soil pH",
  pch = 19,
  col = "steelblue"
)
```

Next, continue to [Data processing and visualisation in R](/materials/data-processing-visualisation/).

[Back to workshop materials](/resources/)
