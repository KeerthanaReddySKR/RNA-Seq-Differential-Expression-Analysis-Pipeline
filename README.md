# RNA-Seq Differential Expression Analysis Pipeline

This project implements a complete RNA-Seq analysis pipeline starting from raw sequencing data to biological insights using differential gene expression analysis.

## 📌 Overview
This pipeline includes:
- Data retrieval from NCBI SRA
- Quality control (FastQC)
- Adapter trimming (Trimmomatic)
- Differential expression analysis (DESeq2)
- Visualization (Volcano plot, PCA, Heatmap)

## 🧬 Dataset
- SRA Accession: SRR957824, SRR5924196
- Data retrieved using SRA Toolkit

## ⚙️ Pipeline Steps

### 1. Data Retrieval
- Tool: SRA Toolkit
- Output: FASTQ files

### 2. Quality Control
- Tool: FastQC
- Checked:
  - Per base quality
  - GC content
  - Sequence duplication

### 3. Adapter Trimming
- Tool: Trimmomatic
- Improved read quality and removed adapters

### 4. Differential Expression Analysis
- Tool: DESeq2 (R)
- Identified:
  - Upregulated genes
  - Downregulated genes

## 📊 Results

- Volcano Plot → Significant DEGs
- PCA Plot → Sample clustering
- Heatmap → Gene expression patterns

## 🧠 Key Insights
- Clear separation between conditions in PCA
- Significant DEGs identified using statistical thresholds

## 🛠 Tech Stack
- R (DESeq2)
- Python (optional processing)
- FastQC
- Trimmomatic

## 🚀 Status
Ongoing – being extended toward publication-level analysis
