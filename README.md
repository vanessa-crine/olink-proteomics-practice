# Olink proteomics practice: QC, normalisation, biomarkers, longitudinal models and machine learning in R

Two Quarto reports that apply an Olink plasma proteomics pipeline in R.

| Report | Data | What it shows |
|---|---|---|
| `01_olinkanalyze_example.qmd` | OlinkAnalyze example data (`npx_data1`, `npx_data2`) | QC, LOD filtering, PCA/UMAP, **bridging normalisation** of two batches, t-tests, mixed models, pathway enrichment |
| `02_mgh_covid_olink.qmd` | MGH COVID-19 cohort, Olink Explore 1536 (~1,400 proteins, 383 patients, Day 0/3/7) | Protein and sample QC, PCA, hierarchical clustering, per-protein regression with FDR, GSEA/ORA, **mixed models of protein trajectories**, **elastic net with nested cross-validation** |

## Data

- `npx_data1` and `npx_data2` come with the R package `OlinkAnalyze`.
- MGH COVID-19 data (Filbin et al., *Cell Reports Medicine* 2021): download the three files from [Mendeley Data, doi 10.17632/nf853r8xsj](https://data.mendeley.com/datasets/nf853r8xsj/2) into a `data/` folder:
  - `Olink Proteomics.xlsx`
  - `Supplemental-Table-2-Olink-Assays-NPX-values_v2.xlsx`
  - `Clinical Metadata.xlsx`

  The data are not included in this repository.

## How to run

Install the packages once:

```r
install.packages(c("OlinkAnalyze", "tidyverse", "readxl", "broom", "lme4", "lmerTest",
                   "glmnet", "pROC", "pheatmap", "ggrepel", "msigdbr", "umap"))
install.packages("BiocManager"); BiocManager::install("clusterProfiler")
```

Then open a `.qmd` file in RStudio and click **Render**.

## Author

Vanessa Crine

## Acknowledgements

Code was drafted with help from Claude (Anthropic), an AI assistant. I ran, checked and interpreted every step myself.
