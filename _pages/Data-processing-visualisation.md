---
title: "Microbiome data exploration and visualisation in R"
excerpt: "A route through the R and microbiome analysis activities."
permalink: /materials/data-processing-visualisation/
layout: single
---

Use [Exploring a soil microbiome in R](https://mulquabio.github.io/MQB/notebooks/microbiome-analysis.html) as the practical for the data management, processing and analysis sessions. The practical contains links to the data, metadata and supporting MulQuaBio sections. For R basics, use the [R introduction guide](https://docs.google.com/document/d/1FPBJ6p946MFAMDNWkASRLofh_lEbVb12/edit?usp=sharing&ouid=103851654386762616794&rtpof=true&sd=true).

## Wednesday 28 October

### 11:30–13:00: Managing and inspecting microbiome data in R

Set up `code/`, `data/` and `results/`, download the data and metadata, and set the practical folder as the working directory in the RStudio Console. Read the question and metadata, import and inspect the data, and discuss what each row and column represents. Start separating sample information from OTU counts, keeping the original file unchanged.

### 14:00–16:00: Exploring and visualising microbiome data in R

Finish checking the two tables. Explore soil moisture across depth and liming categories, starting with a base R plot and then using `ggplot2`. Discuss how relationships between environmental variables can affect interpretation. Remove OTUs with no recorded sequences, calculate sequencing totals and richness, and explore their distributions. Save the analysis commands in your script.

## Optional preparation before Friday

If you have free time after Wednesday's sessions, finish or revisit the setup, checks and environmental plots. You can also read **From richness to diversity** in the practical and try the two-OTU example and Simpson diversity calculation. This is optional: Friday starts with a recap. Thursday's field and laboratory sessions remain as scheduled; you do not need to meet as a group during your free time.

## Friday 30 October

In the morning, revisit any setup difficulties, then explore richness, diversity and rank-abundance plots. In the second practical session, compare richness and diversity with moisture, depth, liming and pesticide treatment; develop hypotheses and consider suitable statistical approaches. You do **not** need to perform the statistical tests.

The 12 students will work in **three groups of four**. Share and rotate coding, checking and interpretation. Each group should prepare one reproducible R script and choose two or three figures for its presentation. Present the question, patterns and variation, hypothesis, an alternative explanation, a proposed statistical approach, and the main limitations, including relationships between environmental variables and the missing sampling-design information.

The group presentation session runs **14:00–15:00**: allow each group 10 minutes to present and 5 minutes for questions, with the remaining 15 minutes for setup and shared discussion. See the [programme](/programme/) for the full schedule.

[Back to workshop materials](/resources/)
