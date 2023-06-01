
<!-- README.md is generated from README.Rmd. Please edit that file -->

# PICsnATAC

<!-- badges: start -->
<!-- badges: end -->

The goal of PICsnATAC is to accurately quantify snATAC-seq data. The two
key components are:

1.  **Constructing cell-by-peak matrix** with Paired Insertion Counting
    (PIC).

*This counting approach is a uniform counting choice for various assays,
including 10X Genomics snATAC-seq, sci-ATAC-seq, SNARE-seq,
dsc-ATAC-seq, s3-ATAC-seq, and scNANO-ATAC.*

2.  Conducting **Differential Accessible Region (DAR)** identification
    analysis using the PIC matrix.

*Building upon our model-based insertion rate estimation framework, this
analysis provides a more sensitive test of DAR between cell groups (cell
types).*

## Dependencies

Please install the dependent libraries by running the following codes

``` r
install.packages('data.table') ## (please make sure it is newer than 1.8)
if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install("GenomicRanges")
```

## Installation

You can install the development version of PICsnATAC from
[GitHub](https://github.com/Zhen-Miao/PIC-snATAC) with:

``` r
# install.packages("devtools")
devtools::install_github("Zhen-Miao/PIC-snATAC")
```

## Example

This is a basic example which shows you how to construct PIC-based cell
by peak matrix:

``` r
library('PICsnATAC')

pic_matrix <- PIC_counting(cells, fragment_tsv_gz_file_location, peak_sets)
```

## Vignette and Interactive Notebooks

Notebook 1: [Run PIC counting on PBMC
data.](https://github.com/Zhen-Miao/PIC-snATAC/blob/main/vignettes/Run_PIC_counting_on_pbmc_3k_data.ipynb)

Notebook 2: [Run PIC DAR on SNARE-seq2 brain
data.](https://github.com/Zhen-Miao/PIC-snATAC/blob/main/vignettes/Run_PIC_on_human_brain_data.ipynb)

*You can run the above notebooks with Google Colab (processed example
data and link provided), but it is recommended that you run it using
computing cluster for large datasets*

Vignette 1: [PIC counting from Cell Ranger
output.](https://htmlpreview.github.io/?https://github.com/Zhen-Miao/PIC-snATAC/blob/main/vignettes/vignette-1----PIC-counting-with-10X-Cell-Ranger-output.html)

Vignette 2: [PIC counting in Seurat/Signac
workflow.](https://htmlpreview.github.io/?https://github.com/Zhen-Miao/PIC-snATAC/blob/main/vignettes/vignette-2----PIC-counting-in-Seurat-workflow.html)

Vignette 3: [PIC counting in ArchR
workflow.](https://htmlpreview.github.io/?https://github.com/Zhen-Miao/PIC-snATAC/blob/main/vignettes/vignette-3----PIC-counting-in-ArchR-workflow.html)

vignette 4: [PIC counting with dsc-ATAC-seq
data.](https://htmlpreview.github.io/?https://github.com/Zhen-Miao/PIC-snATAC/blob/main/vignettes/vignette-4----PIC-counting-with-dsc-ATAC-seq-data.html)

vignette 5: [DAR test with PIC parametric test
framework.](https://htmlpreview.github.io/?https://github.com/Zhen-Miao/PIC-snATAC/blob/main/vignettes/vignette-5----DAR-analysis-with-PIC-parametric-framework.html)
