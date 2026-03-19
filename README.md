# RNA-Seq Differential Expression Analysis Pipeline

## Overview

This project presents a complete, reproducible RNA-seq analysis workflow, starting from raw sequencing data retrieval to statistically robust identification of differentially expressed genes (DEGs).

The pipeline integrates data acquisition, quality assessment, preprocessing, and differential expression analysis to extract biologically meaningful insights from high-throughput sequencing data.

---

## Objectives

* Retrieve raw sequencing data from public repositories
* Perform comprehensive quality assessment of sequencing reads
* Improve data quality through preprocessing and adapter trimming
* Apply statistical modeling to identify differentially expressed genes
* Generate interpretable visualizations for biological insights

---

## Methodology

### 1. Data Retrieval

* Raw sequencing data was obtained from the NCBI Sequence Read Archive (SRA)
* Data was downloaded using `prefetch` and converted to FASTQ format using `fasterq-dump`
* Structured directory organization ensured reproducibility

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
* Presence of sequencing biases and potential adapter contamination

---

### 3. Preprocessing (Trimmomatic)

* Removed adapter sequences
* Trimmed low-quality bases from reads
* Filtered poor-quality reads

**Result:**

* Improved base quality across reads
* Reduction in noise and technical artifacts
* Enhanced suitability for downstream analysis

---

### 4. Differential Expression Analysis (DESeq2)

* Imported count matrix and sample metadata
* Preprocessed data:

  * Removed genes with zero counts
  * Handled missing values appropriately
* Constructed DESeq2 dataset with condition-based design
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

  * Displays significance vs fold change
  * Highlights significantly regulated genes

* **Principal Component Analysis (PCA)**

  * Demonstrates variance and clustering between samples

* **Heatmap**

  * Shows gene expression patterns across conditions

---

## Key Results

* Clear separation between biological conditions observed in PCA
* Identification of statistically significant gene expression changes
* Improved data quality post preprocessing directly enhanced analysis reliability
* Visualization confirmed biologically meaningful clustering and expression patterns

---

## Tools and Technologies

* SRA Toolkit
* FastQC
* Trimmomatic
* R (DESeq2, EnhancedVolcano)

---

## Reproducibility

* Structured pipeline ensures reproducibility
* Standard bioinformatics tools and statistical methods used
* All intermediate and final outputs documented

---

## Research Significance

This project demonstrates:

* End-to-end RNA-seq data analysis capability
* Handling of real-world sequencing datasets
* Application of statistical models for biological inference
* Ability to extract meaningful biological insights from transcriptomic data

---


## Future Scope

* Integration with multi-omics datasets (genomics + proteomics)
* Network-based analysis of DEGs
* Functional enrichment and pathway analysis
