<div align="center">

<img src="https://img.shields.io/badge/CLINICA%20CHIMICA%20ACTA-SUPPLEMENTARY%20MATERIAL-555BA6?style=for-the-badge&amp;labelColor=333333" alt="Clinica Chimica Acta — Supplementary Material" />

[![DOI](https://zenodo.org/badge/1437428675.svg)](https://doi.org/10.5281/zenodo.23740272)


<h1>LabRI: a data-source-agnostic, multi-method statistical consensus framework for laboratory reference interval estimation</h1>

<p><strong>Datasets · Analytical scripts · Study reports</strong></p>

<p>
  <img src="https://img.shields.io/badge/R-4.6.1-0078B4?style=flat-square&amp;logo=r&amp;logoColor=white" alt="Study environment: R 4.6.1" />
  <img src="https://img.shields.io/badge/Data-Real%20%2B%20simulated-555BA6?style=flat-square" alt="Real-world and simulated datasets" />
  <img src="https://img.shields.io/badge/Methods-5-0078B4?style=flat-square" alt="Five evaluated methods" />
  <a href="https://github.com/labrgrupo/Supplementary_Material_CCA_LabRI/commits"><img src="https://img.shields.io/github/last-commit/labrgrupo/Supplementary_Material_CCA_LabRI?style=flat-square&amp;color=555BA6" alt="Latest repository update" /></a>
</p>

<p>
  <a href="#download">Download</a> ·
  <a href="#associated-article">Article</a> ·
  <a href="#package-contents">Contents</a> ·
  <a href="#study-datasets">Datasets</a> ·
  <a href="#reproducing-the-study">Reproducibility</a> ·
  <a href="#related-software">Software</a> ·
  <a href="#citation">Citation</a>
</p>

</div>

---

<div align="justify">

## Download

The complete supplementary material referenced in the manuscript is available in **release v1.0.0**, in the attached archive **`Supplementary_Material_CCA_LabRI.zip`**.

<div align="center">

<a href="https://github.com/labrgrupo/Supplementary_Material_CCA_LabRI/releases/tag/Supplementary_Material_CCA_LabRI_v1.0.0">
  <img src="https://img.shields.io/badge/VIEW%20RELEASE-DOWNLOAD%20SUPPLEMENTARY%20MATERIAL-0078B4?style=for-the-badge&amp;labelColor=555BA6" width="520" alt="Open release v1.0.0 to download the complete supplementary material" />
</a>

</div>

On the release page, expand **Assets**, download the named ZIP, and extract its contents while preserving the folder structure. The automatically generated **Source code** archives contain the repository files and do not include the supplementary ZIP attached to the release.

## Overview

<img src="logo_LabRI.png" width="250" align="right" alt="LabRI logo" />

This repository documents the supplementary research materials supporting the **LabRI** study associated with *Clinica Chimica Acta*. The complete material is distributed as a ZIP package through the release described below.

**LabRI (Laboratory Reference Interval)** is a data-source-agnostic, multi-method statistical consensus framework implemented in R/Shiny. Its estimation workflow combines preprocessing, cluster-driven truncation, complementary reference-limit estimators, consensus rules, and statistical uncertainty assessment.

The study compares **LabRI, Truncated Minimum Chi-square (TMC), Truncated Maximum Likelihood (TML), refineR, and reflimR** using the **PRIDe-RL** comparison framework.

<br clear="all" />

## Associated article

| Item | Details |
| :--- | :--- |
| **Authors** | Alan Carvalho Dias; Luisane Maria Falci Vieira; Derliane de Oliveira; Claudia Maria Meira Dias; João Rodrigo Campos; Daniane Grando Remor Canalli; Tatiana Ferreira de Almeida; Adâmara Felício |
| **Journal** | *Clinica Chimica Acta* |

The article DOI and final publication details will be added when available.

## Package contents

| Material | Description |
| :--- | :--- |
| **Study datasets** | Real-world data (Group 1) and simulated data (Group 2). |
| **Supplementary documentation** | Supporting methodological content referenced in the manuscript. |
| **DataSampleR** | `DataSampleR.Rmd`: reproducible random subsampling with a fixed seed. |
| **Comparator reports · PDF** | TMC, TML, and refineR estimates generated through ReferenceRangeR; reflimR estimates generated through VeRIf. |
| **LabRI reports · HTML** | Analytical workflow, reference interval estimates, and associated uncertainty. |

## Study datasets

### Group 1 · Real-world data

Group 1 comprises **12 analytes** from published studies in which reference intervals were established using directly selected reference individuals. The reference intervals reported in those publications were adopted as the **comparative references (CRs)**.

| Original study | Analytes evaluated | Source |
| :--- | :--- | :--- |
| **Omuse et al., 2020**<br />Kenya | Lactate dehydrogenase (**LDH**), total calcium (**Ca**), amylase (**AMY**), free thyroxine (**FT4**), and thyroid-stimulating hormone (**TSH**). | [Original publication](https://doi.org/10.1371/journal.pone.0235234) |
| **Abbam et al., 2021**<br />Ghana | Alanine aminotransferase (**ALT**), gamma-glutamyl transferase (**GGT**), hemoglobin (**Hb**), absolute lymphocyte count (**LYM**), platelet count (**PLT**), red blood cell count (**RBC**), and white blood cell count (**WBC**). | [Original publication](https://doi.org/10.1371/journal.pone.0245585) |

### Group 2 · Simulated data

Group 2 uses three simulated datasets distributed with the `refineR` package. Each scenario was assessed at **five sample sizes**, including its full available size, yielding **15 scenario–sample-size conditions**.

| Scenario | Full dataset<br />size | Non-pathological /<br />pathological | Evaluated sample sizes (*n*) | Source |
| :--- | ---: | :---: | :--- | :--- |
| **`testcase1`** | 10,000 | 80% / 20% | 500 · 1,000 · 2,000<br />5,000 · 10,000 | [Documentation](https://search.r-project.org/CRAN/refmans/refineR/html/testcase1.html) |
| **`testcase2`** | 50,000 | 60% / 40% | 500 · 1,000 · 5,000<br />10,000 · 50,000 | [Documentation](https://search.r-project.org/CRAN/refmans/refineR/html/testcase2.html) |
| **`testcase4`** | 100,000 | 90% / 10% | 500 · 1,000 · 5,000<br />10,000 · 100,000 | [Documentation](https://search.r-project.org/CRAN/refmans/refineR/html/testcase4.html) |

The reference interval documented for each simulated non-pathological population was adopted as its CR. Smaller datasets were obtained by fixed-seed subsampling with **DataSampleR**, rather than independent simulation at each sample size.

## Comparative performance assessment

The **Performance Ranking by Index of Deviation of Reference Limits (PRIDe-RL)** framework evaluates the difference between each estimated reference limit and its CR, expressed in units of the corresponding **permissible difference (pD)**.

In this study, equivalence intervals were defined using a standard-normal coverage factor of **1.645**, corresponding to approximately **90% central coverage**. A reference limit is conforming when its absolute deviation index is **≤ 1**.

Performance is summarized by **Conformity (d1), Proximity (d2), Tail behavior (d3), and Severity (d4)**. The composite score prioritizes the number of conforming limits, with the geometric mean of d2–d4 as a secondary component. A heatmap displays the direction and magnitude of deviations.

Statistical uncertainty was assessed separately using the ratio of each reference limit's **90% confidence interval width** to the **central 95% reference interval width** (*W*<sub>CI</sub>/*W*<sub>RI</sub>).

## Reproducing the study

### Study environment

| Software | Version used in the study |
| :--- | :--- |
| **R** | 4.6.1 |
| **RStudio** | 2026.09.0+174 |

### Suggested workflow

1. **Obtain the supplementary materials.** Download and extract the complete release package as described under [Download](#download).
2. **Select the dataset group.** Use the supplied real-world data or the simulated testcase and sample-size condition of interest. Preserve the measurement units and comparative reference limits used in the study.
3. **Reproduce subsampling when needed.** Open `DataSampleR.Rmd` in RStudio and retain the fixed seed and sampling settings supplied with the study materials. The same random seed requires the same input data and sampling procedure to reproduce a subsample.
4. **Inspect the original reports.** Use the comparator PDF reports and LabRI HTML reports to trace the estimates reported in the manuscript.
5. **Run the associated software for reanalysis.** Follow the installation and execution instructions in the [application repositories](#related-software). Match the study's inputs and analytical settings when comparing results.

> **Version tracking**  
> When reusing these materials, record the supplementary release version, application versions, package versions, input datasets, random seed, and analytical settings. Later software updates may produce results that differ from the archived study reports.

## Related software

Application source code and installation instructions are maintained separately:

| Tool | Local execution | Web deployment |
| :--- | :--- | :--- |
| **LabRI** — reference interval estimation and verification | [LabRI_shiny](https://github.com/labrgrupo/LabRI_shiny) | [LabRI_shiny_connect](https://github.com/labrgrupo/LabRI_shiny_connect) |
| **PRIDe-RL** — comparative evaluation of reference-limit estimates | [PRIDe-RL_shiny](https://github.com/labrgrupo/PRIDe-RL_shiny) | [PRIDE-RL_shiny_connect](https://github.com/labrgrupo/PRIDE-RL_shiny_connect) |

**Local implementations** automatically save generated figures, tables, and HTML reports to the local file system. **Web-deployment implementations** use session-specific temporary storage and allow reports to be viewed and downloaded through the browser.

The present study focuses on the **LabRI estimation workflow and comparative performance**. The complete multilevel verification module is outside the study's scope.

<div align="center">

<a href="https://grupolabr.com/"><img src="https://img.shields.io/badge/Documentation%20%26%20tutorials-Grupo%20Lab%20R-0078B4?style=for-the-badge&amp;labelColor=555BA6" alt="Visit Grupo Lab R for documentation and tutorials" /></a>

</div>

## Contact

| Contact | Email |
| :--- | :--- |
| **Alan Carvalho Dias** · Corresponding author | [alancdias@hotmail.com](mailto:alancdias@hotmail.com) |
| **Grupo Lab R** | [labrgrupo@gmail.com](mailto:labrgrupo@gmail.com) |

For questions about these materials or reproducibility, contact the corresponding author or use the repository's [Issues page](https://github.com/labrgrupo/Supplementary_Material_CCA_LabRI/issues).

</div>

---

<div align="center">
<sub><strong>LabRI · Supplementary Material</strong><br />Supporting transparency, traceability, and reproducibility in reference interval research.</sub>
</div>
