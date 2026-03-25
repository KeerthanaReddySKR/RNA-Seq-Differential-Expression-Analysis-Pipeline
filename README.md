# RNA-Seq Differential Expression Analysis Pipeline

## Overview

This project presents a complete, reproducible RNA-seq analysis , starting from raw sequencing data retrieval to statistically robust identification of differentially expressed genes (DEGs).

The pipeline integrates data acquisition, quality assessment, preprocessing, and differential expression analysis to extract biologically meaningful insights from high-throughput sequencing data.

---

## Objectives

* Retrieve raw sequencing data from public repositories
* Perform comprehensive quality assessment of sequencing reads
* Improve data quality through preprocessing and adapter trimming
* Apply statistical modeling to identify differentially expressed genes
* Generate interpretable visualizations for biological insights

---

## Computational Environment

All analyses were performed in a Linux-based environment using command-line tools and scripting.

* Operating System: Linux
* Tools executed via terminal (SRA Toolkit, FastQC, Trimmomatic)
* Workflow implemented using shell commands and R scripts
* Data handling and preprocessing performed using command-line pipelines

This reflects standard bioinformatics practices used in real-world research environments.

---

## Methodology

### 1. Data Retrieval (SRA Toolkit)

* Raw sequencing data was obtained from the NCBI Sequence Read Archive (SRA)
* Data downloaded using `prefetch`
* Converted `.sra` files into FASTQ format using `fasterq-dump`
* Organized into structured directories for reproducibility

---

### 2. Quality Assessment (FastQC)

* Performed initial quality analysis using FastQC
* Evaluated key metrics:

  * Per base sequence quality
  * GC content distribution
  * Sequence length distribution
  * Sequence duplication levels
  * Adapter contamination

**Observation:**

* Decline in read quality towards the 3’ end
* Presence of sequencing bias and adapter contamination

---

### 3. Preprocessing (Trimmomatic)

* Removed adapter sequences
* Trimmed low-quality bases
* Filtered poor-quality reads

**Result:**

* Improved base quality across reads
* Reduction in noise and technical artifacts
* Enhanced data quality for downstream analysis

---

### 4. Differential Expression Analysis (DESeq2)

* Loaded count matrix and sample metadata
* Preprocessed data:

  * Removed genes with zero counts
  * Handled missing values appropriately
* Constructed DESeq2 dataset with design: `~ condition`
* Performed:

  * Normalization of counts
  * Dispersion estimation
  * Negative binomial modeling

---

### 5. Identification of Differentially Expressed Genes

Genes were classified based on statistical thresholds:

* **Upregulated Genes:**

  * log2 Fold Change > 1
  * Adjusted p-value < 0.05

* **Downregulated Genes:**

  * log2 Fold Change < -1
  * Adjusted p-value < 0.05

**Outputs Generated:**

* `Upregulated.csv`
* `Downregulated.csv`
* `All_DEGs.csv`

---

### 6. Data Visualization

* **Volcano Plot**

  * Displays statistical significance vs fold change
* **Principal Component Analysis (PCA)**

  * Shows clustering and variance between samples
* **Heatmap**

  * Visualizes expression patterns across conditions

---

## Key Results

* Clear separation between biological conditions observed in PCA
* Identification of statistically significant gene expression changes
* Improved data quality after preprocessing significantly enhanced analysis reliability
* Visualization confirmed meaningful clustering and gene expression patterns

---

## Tools and Technologies

* Linux (Command-line environment)
* SRA Toolkit
* FastQC
* Trimmomatic
* R (DESeq2, EnhancedVolcano)

---

## Reproducibility

* Structured pipeline ensures reproducibility
* Standard bioinformatics tools and statistical methods used
* Clear workflow from raw data to final results

---

## Research Significance

This project demonstrates:

* End-to-end RNA-seq data analysis capability
* Handling of real-world sequencing datasets
* Application of statistical models for biological inference
* Ability to extract meaningful biological insights from transcriptomic data

---

## Future Scope

* Integration with multi-omics datasets
* Network-based analysis of DEGs
* Functional enrichment and pathway analysis
