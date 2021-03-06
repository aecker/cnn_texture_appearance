# Code and data for "A parametric texture model based on deep convolutional features closely matches texture appearance for humans" by Wallis et al.

[![DOI](https://zenodo.org/badge/86071293.svg)](https://zenodo.org/badge/latestdoi/86071293)

This repository contains the code necessary to reproduce the results of 

Wallis, Funke, Ecker, Gatys, Wichmann and Bethge (in press). A parametric texture model based on deep convolutional features closely matches texture appearance for humans. *Journal of Vision*.

A preprint corresponding to the paper can be found at:

https://doi.org/10.1101/165761

Stimuli can be found in a complementary archive (http://doi.org/10.5281/zenodo.438031; stored separately due to license restrictions on images).

## Directory structure of this repository

* `code` = code for generating stimuli, running experiment, and analysing data.
* `documentation` = some testing protocols and subject demographics
* `figures` = some figures from the paper (data figures produced by the `knitr` document)
* `raw_data` = raw data from the experiments.
* `results` = processed data from the experiments

Because the fitted brms/Stan RData files were too large for git, they are attached to the release as a .zip file. To knit the document you should place these into the appropriate results subdirectory (i.e. `results/experiment_11/` and `results/experiment_12`).

## The article 

The manuscript was produced using knitr (Xie, 2013; 2015). The main file is `texture_discrimination_manuscript.Rnw`. You can look in here for the bare text of the manuscript, plus all the associated R code for generating figures and the numbers in the paper.

With all appropriate packages installed, "knitting" this will produce 

- a .tex file `texture_discrimination_manuscript.tex`
- a .pdf file `texture_discrimination_manuscript.pdf`
- a subdirectory `cache/`, featuring cached results
- a subdirectory `figure/`, featuring features automagically generated by the embedded R code.

Xie, Y. (2013). knitr: A comprehensive tool for reproducible research in R. BT - Implementing Reproducible Computational Research. In V. Stodden, F. Leisch, & R. D. Peng (Eds.), Implementing Reproducible Computational Research. Chapman & Hall/CRC. 

Xie, Y. (2015). Dynamic Documents with R and Knitr, Second Edition (2nd ed.). Chapman & Hall/CRC.

I looked into using [packrat](https://rstudio.github.io/packrat/) for this project but had troubles with some library compilation (incompatible clang; apparently an OSX problem). I hope the version numbers reported in the paper suffice.

## Generating new stimuli 

The code to generate stimuli from the CNN texture model can be found at https://github.com/leongatys/DeepTextures

## Experiment labelling

Note that Experiment 1 from the paper corresponds to `experiment_11` in the code and Experiment 2 in the paper corresponds to `experiment_12` in the code. We ran related but separate experiments that were stored in the same repository. I've kept the code as-is to reduce the need to relabel directories.

To run the code in your own setup you will need to adjust top directory paths to the relevant path on your local machine. Look for the variable `top_dir` in most scripts; that should suffice. If you know of a nicer way to handle this please let me know (RStudio projects work for the bulk, but will create a different working directory than for knitting documents).



