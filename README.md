# DeepPheno_Luma-Iva

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20837397.svg)](https://doi.org/10.5281/zenodo.20837397)

## Longitudinal multi-omic profiling of pediatric cystic fibrosis during lumacaftor/ivacaftor therapy

This repository contains processed data, metadata, and R analysis scripts from a prospective longitudinal phase IV pilot study of pediatric patients with cystic fibrosis (CF) receiving lumacaftor/ivacaftor (LUMA/IVA).

Eight children with cystic fibrosis homozygous for the **F508del CFTR mutation** were followed for up to **24 months** after initiation of lumacaftor/ivacaftor therapy.

The study integrates repeated measurements across multiple biological domains, including:

- clinical and anthropometric measurements
- lung function
- sweat chloride
- routine clinical laboratory measurements
- systemic and respiratory inflammatory markers
- conventional respiratory microbiology
- stool microbiome
- sputum microbiome
- throat-swab microbiome
- serum metabolomics

The repository accompanies the Data in Brief dataset article:

> **A longitudinal multi-omic dataset of pediatric cystic fibrosis patients receiving lumacaftor/ivacaftor therapy: clinical, microbiome, inflammatory and metabolomic measurements collected over 24 months**

The study was registered in the German Clinical Trials Register under **DRKS00022267**.

---

## Persistent archive and DOI

A permanent, citable release of this repository is archived on Zenodo:

**DOI: [10.5281/zenodo.20837397](https://doi.org/10.5281/zenodo.20837397)**

The Zenodo archive provides a persistent snapshot of the released repository independent of future changes to the GitHub repository.

When using the processed data or analysis code from this repository, please cite the Zenodo DOI.

---

## Study design

The dataset contains longitudinal measurements from eight children with cystic fibrosis homozygous for the F508del mutation who initiated lumacaftor/ivacaftor therapy.

Participants were followed for up to nine visits over 24 months:

| Visit | Time relative to treatment initiation |
|---|---|
| V1 | Baseline |
| V2 | 3 months |
| V3 | 6 months |
| V4 | 9 months |
| V5 | 12 months |
| V6 | 15 months |
| V7 | 18 months |
| V8 | 21 months |
| V9 | 24 months |

Clinical measurements and biospecimens collected across the study included:

- blood/serum
- stool
- sputum
- deep throat swabs
- sweat chloride
- lung-function measurements
- anthropometric measurements
- clinical and medication metadata

All eight participants completed the first 12 months of follow-up. Sample and participant availability decreased at later visits because of COVID-19 restrictions and participant availability.

Not every participant was able to provide every sample type at every visit, particularly sputum samples.

---

# Data availability

### Processed data and analysis code

GitHub:

https://github.com/RebeccaLuise/DeepPheno_Luma-Iva

Permanent Zenodo archive:

https://doi.org/10.5281/zenodo.20837397

### Raw 16S rRNA sequencing data

Raw sequencing data from stool, sputum, and throat-swab samples are publicly available through the NCBI Sequence Read Archive:

**BioProject: PRJNA1119982**

https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1119982

### Raw serum metabolomics data

Raw mass-spectrometry data are publicly available through MassIVE:

**MassIVE accession: MSV000094922**

https://massive.ucsd.edu/ProteoSAFe/dataset.jsp?task=MSV000094922

Raw sequencing and mass-spectrometry files are not duplicated in this repository. This repository provides the processed analytical datasets, metadata, and analysis workflows used for downstream analyses.

---

# Repository structure

The repository contains processed data in the `data/` directory and R Markdown (`.Rmd`) files containing data-processing, statistical-analysis, and visualization workflows.

```text
DeepPheno_Luma-Iva/
│
├── data/
│   └── Processed analytical data and metadata
│
├── ClinicalData.Rmd
├── metadata_16S_fastq.Rmd
├── import_explore_m2_3And4.Rmd
├── Metabolomic_analysis.Rmd
│
├── Fig2.Rmd
├── Fig3.Rmd
├── Fig4.Rmd
│
├── orkambi_kids_visualizations.Rmd
├── orkambi_kids_dominant_taxa.Rmd
├── ggalluvial_dominanceSputum.Rmd
│
└── README.md
```

---

# Description of repository files

The following table provides an overview of the files and their role in the analysis.

| File / directory | Description | Role in the analysis |
|---|---|---|
| `data/` | Processed analytical data and metadata used by the R Markdown workflows. The repository contains processed clinical, microbiome, metabolomics, and associated metadata. | Input data for the downstream analyses and figure-generation workflows. |
| `ClinicalData.Rmd` | Processing, exploration, and visualization of longitudinal clinical phenotype data. | Clinical-data preparation and exploratory analysis supporting the systemic, gastrointestinal, and respiratory analyses. |
| `metadata_16S_fastq.Rmd` | Preparation and organization of metadata associated with the 16S rRNA sequencing samples. | Links microbiome samples to participant, visit, sequencing, and sample-type information. |
| `import_explore_m2_3And4.Rmd` | Import and exploratory processing of microbiome data used in downstream gastrointestinal and respiratory analyses. | Preparation and exploration of microbiome objects for diversity, ordination, and taxonomic analyses. |
| `Metabolomic_analysis.Rmd` | Processing and exploratory/statistical analysis of the untargeted serum metabolomics dataset. | Metabolomics-specific analysis supporting the longitudinal metabolite analyses presented with the systemic measurements. |
| `Fig2.Rmd` | Analysis and visualization of longitudinal systemic measurements. | Analysis corresponding to **Figure 2**, including sweat chloride, serum IgG, leukocyte counts, and selected serum metabolite profiles. |
| `Fig3.Rmd` | Analysis and visualization of longitudinal gastrointestinal measurements and stool microbiome profiles. | Analysis corresponding to **Figure 3**, including BMI z-score, fecal calprotectin, liver enzymes, stool alpha diversity, and Bray-Curtis/NMDS analyses. |
| `Fig4.Rmd` | Analysis and visualization of longitudinal respiratory measurements and respiratory microbiome profiles. | Analysis corresponding to **Figure 4**, including relative change in ppFEV1, sputum inflammatory markers, respiratory microbiome ordination, paired respiratory samples, and PERMANOVA analyses. |
| `orkambi_kids_visualizations.Rmd` | Additional exploratory visualization of the longitudinal microbiome dataset. | Supporting visualization of microbiome composition across participants, visits, and sample types. |
| `orkambi_kids_dominant_taxa.Rmd` | Analysis and visualization of dominant microbial taxa across longitudinal microbiome samples. | Supporting taxonomic-composition analysis. |
| `ggalluvial_dominanceSputum.Rmd` | Visualization of longitudinal changes in dominant taxa in sputum samples using alluvial-style representations. | Supporting visualization of temporal respiratory microbiome composition. |
| `README.md` | Documentation of the repository, data availability, analysis files, and proposed reproducibility workflow. | Starting point for users wishing to understand or reuse the dataset and analysis code. |

---

# Description of the processed data

The `data/` directory contains the processed analytical data and metadata used by the R Markdown scripts.

The processed data represented in the repository include the following domains:

### Clinical and participant metadata

Longitudinal participant and visit information and clinical measurements, including, where available:

- age and sex
- BMI and BMI z-score
- ppFEV1 and ppFVC
- sweat chloride
- complete blood counts
- serum immunoglobulins
- inflammatory markers
- liver enzymes
- fecal calprotectin
- conventional respiratory microbiology
- medication information
- antibiotic exposure
- study visit information

### Microbiome data and metadata

Processed 16S rRNA gene sequencing data and associated technical/sample metadata from:

- stool
- sputum
- throat swabs

### Metabolomics data

Processed serum metabolomics measurements generated by untargeted mass spectrometry.

Four LC-MS datasets were generated and analyzed separately:

- HILIC negative ionization
- HILIC positive ionization
- reversed-phase (RP) negative ionization
- reversed-phase (RP) positive ionization

Only metabolites annotated based on MS1 and MS2 spectral matching to in-house and/or external databases were included in the statistical analyses described in the accompanying article.

---

# Analysis represented in the repository

## Clinical analyses

Longitudinal clinical measurements include anthropometry, lung function, sweat chloride, blood measurements, inflammatory markers, gastrointestinal measurements, conventional microbiology, and associated clinical metadata.

`ClinicalData.Rmd` provides clinical-data processing and exploratory analyses used to support the downstream domain-specific analyses.

---

## Microbiome analysis

Microbiome profiles were generated from:

- stool
- sputum
- deep throat swabs

DNA was extracted using the DNeasy PowerSoil Pro Kit.

The V4 region of the 16S rRNA gene was amplified using the 515F/806R primer pair and sequenced using an Illumina MiSeq platform.

Amplicon sequence variants (ASVs) were inferred using **DADA2**, and taxonomy was assigned using the **SILVA** database.

Rarefaction analyses were used to assess sequencing depth, and samples containing fewer than **2,000 reads** were excluded.

The downstream analyses represented in this repository include taxonomic composition, alpha diversity, Bray-Curtis dissimilarity, ordination, dominant-taxa analyses, and PERMANOVA.

---

## Metabolomics analysis

Untargeted mass spectrometry was used to profile the serum metabolome longitudinally.

Samples were analyzed using:

- HILIC negative
- HILIC positive
- RP negative
- RP positive

Each dataset was analyzed separately.

The processed metabolomics data support exploratory multivariate and univariate analyses and longitudinal visualization of selected metabolite abundances.

The corresponding raw mass-spectrometry files are available through MassIVE under accession **MSV000094922**.

---

# Relationship between repository files and article figures

The primary figure-generation workflows correspond to Figures 2–4 of the accompanying dataset article.

| Article component | Measurements / analysis | Main repository file |
|---|---|---|
| **Figure 2 – Longitudinal systemic measurements** | Sweat chloride, serum IgG, leukocyte counts, selected serum metabolites | `Fig2.Rmd` |
| **Figure 3 – Gastrointestinal measurements and stool microbiome** | BMI z-score, fecal calprotectin, ASAT/AST, ALAT/ALT, stool Shannon diversity, Bray-Curtis/NMDS | `Fig3.Rmd` |
| **Figure 4 – Respiratory measurements and respiratory microbiome** | Relative ppFEV1 change, sputum inflammatory markers, respiratory microbiome composition, Bray-Curtis ordination, PERMANOVA | `Fig4.Rmd` |
| Clinical-data preparation | Longitudinal clinical phenotype data | `ClinicalData.Rmd` |
| Serum metabolomics | Processed untargeted metabolomics measurements | `Metabolomic_analysis.Rmd` |
| Microbiome metadata | 16S sequencing/sample metadata | `metadata_16S_fastq.Rmd` |
| Microbiome import/exploration | Preparation and exploration of microbiome objects | `import_explore_m2_3And4.Rmd` |
| Additional microbiome visualization | Longitudinal microbiome visualization | `orkambi_kids_visualizations.Rmd` |
| Dominant taxa | Dominant-taxa analysis | `orkambi_kids_dominant_taxa.Rmd` |
| Sputum taxa dynamics | Longitudinal alluvial visualization | `ggalluvial_dominanceSputum.Rmd` |

---

# Proposed workflow for reproducing the data analysis

The following workflow provides a logical route for reproducing the analyses from the **processed data** distributed with this repository.

Because the repository contains analyses from several biological domains, the clinical, microbiome, and metabolomics workflows can initially be processed separately before being combined in the figure-specific analyses.

## Step 1 — Obtain the repository

Clone the GitHub repository:

```bash
git clone https://github.com/RebeccaLuise/DeepPheno_Luma-Iva.git
cd DeepPheno_Luma-Iva
```

Alternatively, obtain the archived release from Zenodo:

https://doi.org/10.5281/zenodo.20837397

---

## Step 2 — Inspect the processed input data

Processed analytical datasets and metadata are located in:

```text
data/
```

These files provide the starting point for reproducing the downstream statistical analyses and visualizations.

Users wishing to reproduce analyses from the raw molecular measurements should instead begin with the raw SRA and/or MassIVE data described under **Raw data availability**.

---

## Step 3 — Prepare and explore the clinical data

Use:

```text
ClinicalData.Rmd
```

This workflow processes and explores the longitudinal clinical phenotype data used by subsequent analyses.

The clinical data include variables related to:

- anthropometry
- lung function
- sweat chloride
- systemic measurements
- gastrointestinal measurements
- respiratory measurements
- inflammatory markers
- conventional microbiology

---

## Step 4 — Prepare the microbiome metadata and data objects

Use:

```text
metadata_16S_fastq.Rmd
```

to organize the metadata associated with the 16S rRNA sequencing samples.

Then use:

```text
import_explore_m2_3And4.Rmd
```

for microbiome import, integration, and exploratory processing.

The resulting microbiome data are used for downstream stool and respiratory microbiome analyses.

Conceptually:

```text
Raw/processed 16S data
          │
          ▼
metadata_16S_fastq.Rmd
          │
          ▼
Sample + sequencing metadata
          │
          ▼
import_explore_m2_3And4.Rmd
          │
          ├──────────────► Stool microbiome analyses
          │
          └──────────────► Respiratory microbiome analyses
```

---

## Step 5 — Analyze the serum metabolomics data

Use:

```text
Metabolomic_analysis.Rmd
```

for metabolomics-specific processing and statistical exploration.

The processed metabolomics measurements are subsequently used for the systemic longitudinal metabolite visualizations represented in Figure 2.

---

## Step 6 — Reproduce Figure 2

Use:

```text
Fig2.Rmd
```

The workflow integrates systemic clinical measurements with processed serum metabolomics data.

```text
Clinical/systemic measurements
              │
              ├──────────────┐
              │              │
              │              ▼
              │          Fig2.Rmd
              │              ▲
              │              │
Metabolomics ─┴──────────────┘
                             │
                             ▼
                         Figure 2
                Longitudinal systemic
                     measurements
```

Figure 2 includes:

- sweat chloride concentrations
- serum IgG
- blood leukocyte counts
- selected longitudinal serum metabolite abundances

Exploratory statistical analyses use longitudinal linear mixed-effects models with participant identifier included as a random effect.

---

## Step 7 — Reproduce Figure 3

Use:

```text
Fig3.Rmd
```

This workflow combines gastrointestinal clinical measurements with the processed stool microbiome data.

```text
Clinical/GI measurements ──────┐
                               │
Stool microbiome ───────────────┤
                               │
16S/sample metadata ────────────┤
                               ▼
                           Fig3.Rmd
                               │
                               ▼
                           Figure 3
                   Gastrointestinal data
                    + stool microbiome
```

Figure 3 includes:

- BMI z-score
- fecal calprotectin
- ASAT/AST
- ALAT/ALT
- stool Shannon alpha diversity
- Bray-Curtis beta diversity
- NMDS ordination

---

## Step 8 — Reproduce Figure 4

Use:

```text
Fig4.Rmd
```

This workflow combines respiratory clinical measurements, sputum inflammatory measurements, and respiratory microbiome data.

```text
Respiratory clinical data ──────┐
                                │
Sputum inflammatory data ───────┤
                                │
Sputum microbiome ───────────────┤
                                │
Throat-swab microbiome ──────────┤
                                │
16S/sample metadata ─────────────┤
                                ▼
                            Fig4.Rmd
                                │
                                ▼
                            Figure 4
                     Respiratory measurements
                         + microbiome
```

Figure 4 includes:

- relative change in ppFEV1 compared with baseline
- sputum inflammatory-marker concentrations
- respiratory microbiome composition
- Bray-Curtis-based ordination
- paired sputum/throat-swab comparisons
- PERMANOVA analyses

---

## Step 9 — Run additional microbiome analyses

Additional exploratory analyses are available in:

```text
orkambi_kids_visualizations.Rmd
orkambi_kids_dominant_taxa.Rmd
ggalluvial_dominanceSputum.Rmd
```

These scripts provide additional visualization and taxonomic exploration of the longitudinal microbiome data beyond the primary analyses represented in Figures 3 and 4.

---

# Proposed analysis workflow at a glance

```text
                                  data/
                                    │
               ┌────────────────────┼────────────────────┐
               │                    │                    │
               ▼                    ▼                    ▼
      ClinicalData.Rmd     metadata_16S_fastq.Rmd  Metabolomic_analysis.Rmd
               │                    │                    │
               │                    ▼                    │
               │       import_explore_m2_3And4.Rmd      │
               │                    │                    │
               │           ┌────────┴────────┐           │
               │           │                 │           │
               ▼           ▼                 ▼           ▼
           Fig2.Rmd     Fig3.Rmd          Fig4.Rmd    Fig2.Rmd
               │           │                 │
               ▼           ▼                 ▼
           Figure 2     Figure 3          Figure 4
           Systemic     Gastrointestinal  Respiratory
                        + stool            + respiratory
                        microbiome         microbiome


Additional microbiome exploration:

                 import_explore_m2_3And4.Rmd
                             │
               ┌─────────────┼─────────────┐
               │             │             │
               ▼             ▼             ▼
 orkambi_kids_        orkambi_kids_   ggalluvial_
 visualizations.Rmd   dominant_taxa.Rmd dominanceSputum.Rmd
```

This diagram represents the **logical organization of the analyses** rather than a software dependency graph. Individual R Markdown files should be inspected for their specific input paths and package requirements before execution.

---

Clinical trial registration:

**German Clinical Trials Register — DRKS00022267**

---

# Citation

If you use the processed data, metadata, or analysis code contained in this repository, please cite the archived repository:

> **DeepPheno_Luma-Iva. Zenodo.**  
> DOI: https://doi.org/10.5281/zenodo.20837397

Please also cite the associated Data in Brief dataset article:

> Knoll RL, Rossow V, Rössler J, et al.  
> **A longitudinal multi-omic dataset of pediatric cystic fibrosis patients receiving lumacaftor/ivacaftor therapy: clinical, microbiome, inflammatory and metabolomic measurements collected over 24 months.**  
> *Data in Brief.*

---

# External identifiers

| Resource | Identifier |
|---|---|
| Repository archive | **DOI 10.5281/zenodo.20837397** |
| Clinical trial | **DRKS00022267** |
| Raw 16S sequencing | **NCBI BioProject PRJNA1119982** |
| Raw serum metabolomics | **MassIVE MSV000094922** |

---

# Contact

For questions concerning the dataset or analysis workflows, please use the GitHub Issues section or contact the corresponding authors of the associated publication.
