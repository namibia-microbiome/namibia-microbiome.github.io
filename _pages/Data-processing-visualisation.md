---
title: "Data processing and visualisation in R"
excerpt: "A simple, reproducible workflow for preparing, summarising and plotting data in R."
permalink: /materials/data-processing-visualisation/
layout: single
---

This tutorial introduces a simple workflow for turning raw observations into a
clean table, a summary and a clear figure. It assumes that you have completed
the [R basics tutorial](/materials/r-basics/).

## Learning outcomes

By the end of this tutorial, you should be able to:

- keep raw data separate from derived results;
- inspect and clean a dataset without editing the raw file;
- filter and summarise observations; and
- create and save a clear figure with `ggplot2`.

## 1. Organise your project

A simple project structure makes an analysis easier to understand and repeat:

```text
project/
├── code/       # R scripts
├── data/       # original data; do not edit by hand
└── results/    # cleaned tables and figures
```

## 2. Load and inspect the data

The example below uses the `iris` dataset included with R, so no download is
needed.

```r
data(iris)

head(iris)
dim(iris)
names(iris)
str(iris)
summary(iris)
colSums(is.na(iris))
```

Before changing anything, confirm what one row represents, what each column
means, which units are used and how missing values are recorded.

## 3. Select and clean observations

The following example creates a new object and leaves the original data
unchanged.

```r
clean_data <- subset(
  iris,
  !is.na(Sepal.Length) & Sepal.Length > 0
)

clean_data$Species <- droplevels(clean_data$Species)
```

Use clear object and column names, keep one kind of information in each column,
and write every cleaning step in your script.

## 4. Summarise the data

Install `dplyr` once with `install.packages("dplyr")`, then load it in each new
R session.

```r
library(dplyr)

species_summary <- clean_data |>
  group_by(Species) |>
  summarise(
    samples = n(),
    mean_sepal_length = mean(Sepal.Length),
    sd_sepal_length = sd(Sepal.Length)
  )

species_summary
```

Save derived results separately from the raw data:

```r
write.csv(
  species_summary,
  "results/species_summary.csv",
  row.names = FALSE
)
```

## 5. Create a figure

Install `ggplot2` once with `install.packages("ggplot2")`, then create a simple
plot showing the distribution of observations in each group.

```r
library(ggplot2)

sepal_plot <- ggplot(
  clean_data,
  aes(x = Species, y = Sepal.Length, colour = Species)
) +
  geom_jitter(width = 0.12, alpha = 0.65) +
  geom_boxplot(width = 0.45, alpha = 0.15, outlier.shape = NA) +
  labs(
    x = "Species",
    y = "Sepal length (cm)"
  ) +
  theme_minimal() +
  theme(legend.position = "none")

sepal_plot

ggsave(
  "results/sepal_length_by_species.png",
  sepal_plot,
  width = 7,
  height = 5,
  dpi = 300
)
```

A useful figure should have readable labels, appropriate units and a visual
encoding that makes the comparison clear.

## Further learning

For a more complete treatment of data organisation, reshaping, cleaning and
publication-quality graphics, see the external
[MulQuaBio: Data Management and Visualization in R](https://mulquabio.github.io/MQB/notebooks/data-r.html)
chapter.

[Back to workshop materials](/resources/)
