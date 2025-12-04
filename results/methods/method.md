Translation and Summary
This document describes an RNA-Seq data analysis workflow for studying gene expression in Drosophila melanogaster (fruit fly) samples comparing treated (PS depletion) versus untreated conditions.
Key Steps:
1. Data Loading & Quality Control

Loaded raw RNA-Seq data (FASTQ files) from treated and untreated samples
Checked sequencing quality using Falco/FastQC and MultiQC
Trimmed low-quality sequences with Cutadapt
Verified for duplicates, contamination, and coverage biases

2. Read Mapping

Used RNA STAR to map reads to the Drosophila genome (dm6 build)
STAR accounts for splicing in processed mRNA
Achieved >70% mapping rate
Visualized alignments in IGV

3. Quantification & Strand Determination

Determined library orientation (found to be unstranded)
Counted reads per gene using STAR or featureCounts
~63% of reads successfully assigned to genes

4. Differential Gene Expression (DGE) Analysis

Used DESeq2 to normalize counts and identify differentially expressed genes
Accounted for treatment and sequencing type (paired-end vs single-end)
Generated PCA plots and heatmaps showing sample clustering
Filtered for significant genes (adjusted p-value < 0.05, |Log2FC| > 1)
Annotated results with gene names and locations

Main Goal: Identify genes whose expression significantly changes due to PS depletion treatment.
