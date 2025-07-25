[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.txt)
[![R](https://img.shields.io/badge/Language-R-276DC3?logo=r&logoColor=white)](https://www.r-project.org/)
[![RMarkdown](https://img.shields.io/badge/Notebook-RMarkdown-8c52fc?logo=rstudio)](https://rmarkdown.rstudio.com/)
[![Reproducible Research](https://img.shields.io/badge/Reproducible-Yes-brightgreen)](#reproducibility--reflection)
[![Reference Paper](https://img.shields.io/badge/Reference%20Paper-Nat.Comm.-blue)](https://doi.org/10.1038/s41467-020-19390-9)
[![Last Commit](https://img.shields.io/github/last-commit/NikolaosSamperis/Reconstruction-of-RNA-seq-analysis)](https://github.com/NikolaosSamperis/Reconstruction-of-RNA-seq-analysis/commits/main)


# RNA-Seq Analysis Replication

This repository contains the **reconstruction of the downstream RNA-seq bioinformatics analysis** for  
["Adaptive laboratory evolution of native methanol assimilation in *Saccharomyces cerevisiae*"](https://doi.org/10.1038/s41467-020-19390-9) (Espinosa et al., 2020, Nature Communications).

The project demonstrates the challenges and practices of computational reproducibility by closely following the methods described in the original study and reflecting on any obstacles or discrepancies encountered.

---

## 📄 Full Analysis Report

- **[View the interactive HTML report here](https://nikolaossamperis.github.io/Reconstruction-of-RNA-seq-analysis/project7BBG1002.html)**
- PDF and RMarkdown sources are also included in this repository.

---

## 📂 Repository Structure

```{bash}
.
├── data/
│ ├── Paper_results.csv                      # Results provided by the original study for comparison
│ └── readCounts2.txt                        # Gene-level read counts after featureCounts
├── outputs/
│ ├── fastqc_output/                         # Quality control HTML reports per sample (FastQC, MultiQC)
│ ├── output_plots/
│ │ ├── heatmaps/                            # Heatmap images for gene expression
│ │ ├── volcano_plots/                       # Volcano plot images
│ │ ├── downregulated_path_enrichment/       # KEGG/GO plots for downregulated genes
│ │ └── upregulated_path_enrichment/         # KEGG/GO plots for upregulated genes
│ ├── Paper_results.csv                      # Comparison results vs. original paper
│ └── readCounts2.txt                        # Redundant copy for outputs (legacy)
├── Final_report_with_reflection.pdf         # Full write-up including methods, results, and self-reflection
├── LICENSE.txt                              # MIT License
├── README.md                                # This file
├── project7BBG1002.Rmd                      # RMarkdown for full pipeline and code
├── project7BBG1002.html                     # Rendered HTML notebook/report

```
---

## 📝 Project Overview

This analysis attempts to **reproduce the main findings** of Espinosa et al. (2020), who explored genetic adaptations enabling native methanol assimilation in *S. cerevisiae*.  
We focus on:

- **Replicating the RNA-seq downstream analysis pipeline** (QC, alignment, quantification, differential expression, enrichment analysis)
- Comparing our results to the original study
- Highlighting sources of discrepancy and reflecting on reproducibility challenges in computational biology

---

## 🔗 Reference Paper

**Espinosa MI, Gonzalez-Garcia RA, Valgepea K, et al.**  
[Adaptive laboratory evolution of native methanol assimilation in Saccharomyces cerevisiae. *Nature Communications*, 2020; 11(1):5564.](https://doi.org/10.1038/s41467-020-19390-9)

---

## 🚀 How to Use This Repository

1. **Browse the HTML Report**  
   For a detailed walk-through of the entire pipeline and results, see [project7BBG1002.html](https://nikolaossamperis.github.io/Reconstruction-of-RNA-seq-analysis/project7BBG1002.html).

2. **Explore the Data and Outputs**  
   - `data/` folder contains raw read counts and original paper results
   - `outputs/` contains all figures and quality control summaries

3. **Review the Source Code**  
   - See `project7BBG1002.Rmd` for the full R analysis pipeline (can be re-run in R or RStudio)
   - All required packages and workflow steps are described in the RMarkdown

---

## 🧬 Main Analysis Steps

- **Raw data download** from SRA (PRJNA612896)
- **Quality control** using FastQC and MultiQC
- **Genome alignment** using STAR aligner
- **Quantification** of read counts with featureCounts
- **Differential expression analysis** using DESeq2
- **GO and pathway enrichment** using clusterProfiler (KEGG, GO terms)
- **Comparison** to results reported in the Espinosa et al. paper

See the report for exact code, software versions, and parameter choices.

---

## 🔄 Reproducibility & Reflection

This project not only attempts to reproduce a published bioinformatics workflow, but also documents the obstacles faced, such as:
- Differences in alignment and quantification tools (open-source vs. proprietary)
- Incomplete methodological reporting in the original study
- Database and software accessibility issues (e.g., discontinued YeastMine)
- Ambiguities in statistical thresholds (FDR, p-value, log2FC)
- Technical challenges with data formats and ID mapping

A detailed self-reflection and methodological discussion are included in `Final_report_with_reflection.pdf`.

---

## 📜 License

This project was created for educational purposes as part of coursework.

Feel free to use, modify, and share the code **with proper attribution**. Please note that this project is provided **as-is**, without any warranty or guarantee of functionality.

If you use this code, kindly credit the original author by linking back to this repository.

---

## 🙏 Collaborators & Contributions
This project is developed as part of a group coursework for the *Applied Bioinformatics and Cloud Computing* module. Thanks to my group members for their help on this project.
- Madiha Khan
- Yixin Huang
