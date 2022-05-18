
# Overview of ICGC-ARGO Analysis Pipelines
- [Introduction](#introduction)
- [DNA-Seq Analysis](#dna-seq-analysis)
  - [DNA-Seq Alignment](#dna-seq-alignment)
  - [Sanger WGS Variant Calling](#sanger-wgs-variant-calling)
  - [Sagner WXS Variant Calling](#sagner-wxs-variant-calling)
  - [GATK Mutect2 Variant Calling](#gatk-mutect2-variant-calling)
  - [Open Access Variant Filtering](#open-access-variant-filtering)
  - [Somatic SNV and InDel Variant Calling](#somatic-snv-and-indel-variant-calling)
  - [Stuctural Variant and Copy Number Calling](#stuctural-variant-and-copy-number-calling)
- [RNA-Seq Analysis](#rna-seq-analysis)
  - [RNA-Seq Alignment](#rna-seq-alignment)
  - [RNA-Seq Expression Counting](#rna-seq-expression-counting)
  - [RNA Editing](#rna-editing)
  - [Alternative Promoter Analysis](#alternative-promoter-analysis)
  - [Allele Specific Expression](#allele-specific-expression)
  - [RNA-Seq Splicing](#rna-seq-splicing)
  - [RNA-Seq Data Simulation](#rna-seq-data-simulation)
- [ARGO QC Tools and Workflows](#argo-qc-tools-and-workflows)
- [Mutational Signatures Analysis](#mutational-signatures-analysis)
- [ARGO Reference Files](#argo-reference-files)
- [ARGO Utility](#argo-utility)

## Introduction
- This gives an overview of major ICGC ARGO analysis pipelines which are running in production or with development work in progress. The content will be periodically reviewed and changed over time.  
- Current ARGO production workflows are running in Regional Data Processing Centre (RDPC).
- Each ARGO workflow in the repositories has been tested on accompany test datasets.
- All ARGO analysis workflows are written in [Nextflow](https://www.nextflow.io/) with Dockerized tools.
- All ARGO workflows are published under an GNU AGPL v3 open-source license and are packaged for community usage
- Please check [ICGC ARGO Documentation](https://docs.icgc-argo.org/docs/analysis-workflows/analysis-overview) for more details.

## DNA-Seq Analysis
### DNA-Seq Alignment
- Workflow git repo: https://github.com/icgc-argo-workflows/dna-seq-processing-wfs
- This repository maintains the Nextflow workflow code for BWA-MEM alignment, which can be used for Whole Exome Sequencing (WXS), Whole Genome Sequencing (WGS), Targeted Sequencing, and some other DNA-Seq experimental strategies. The workflow takes either BAM or FASTQ files as inputs, performs reads mapping for each read group, and optional step of MarkDuplicates, then outputs a merged and sorted CRAM file, a CRAM index file, and various QC metrics files.

### Sanger WGS Variant Calling
- Workflow git repo: https://github.com/icgc-argo-workflows/sanger-wgs-variant-calling
- This repository maintains the Nextflow workflow code for Sanger WGS somatic variant calling. The underlying containerized variant calling tools include CaVEMan, Pindel, ASCAT and BRASS, which were originated from https://github.com/cancerit/dockstore-cgpwgs.

### Sagner WXS Variant Calling
- Workflow git repo: https://github.com/icgc-argo-workflows/sanger-wxs-variant-calling
- This repository maintains the Nextflow workflow code for Sanger WXS somatic variant calling. The underlying containerized variant calling tools include CaVEMan and Pindle, which were originated from https://github.com/cancerit/dockstore-cgpwxs.

### GATK Mutect2 Variant Calling
- Workflow git repo: https://github.com/icgc-argo-workflows/gatk-mutect2-variant-calling
- This repository maintains the Nextflow workflow code for Mutect2 somatic variant calling. The underlying variant calling and related tools are originated from GATK https://github.com/broadinstitute/gatk.


### Open Access Variant Filtering
- Workflow git repo: https://github.com/icgc-argo-workflows/open-access-variant-filtering
- This repository maintains the source code of the ICGC ARGO Open-access Somatic Variant Filtering Workflow. It is a bioinformatics workflow that can be used to filter SNV/InDel VCFs based on predefined genomic regions.

### Somatic SNV and InDel Variant Calling
- WIP git repo: https://github.com/icgc-argo-workflows/argo-somatic-variant-calling 
- This repository contains a collection of somatic SNV/InDel variant callers used for various analysis in the context of the ICGC ARGO project.

### Stuctural Variant and Copy Number Calling
- WIP git repo: https://github.com/icgc-argo-workflows/icgc-argo-sv-copy-number
- This repository contains a collection of somatic SV/CNV callers used for various analysis in the context of the ICGC ARGO project.


## RNA-Seq Analysis
### RNA-Seq Alignment
- Workflow git repo: https://github.com/icgc-argo-workflows/rna-seq-alignment
- This repository maintains the Nextflow workflow code for STAR and HiSAT2 RNA-Seq alignment workflows that take either BAM and FASTQ files as inputs, and generates genome aligned CRAM,  Splice Junction Quantifications, and various QC metrics files.


### RNA-Seq Expression Counting
- WIP git repo: https://github.com/icgc-argo-workflows/rna-seq-expression-counting
- This repository contains the packages for RNA-Seq expression-counting/normalization analysis that are part of the ICGC ARGO data analysis pipeline.

### RNA Editing
- WIP git repo: https://github.com/icgc-argo-workflows/rna-editing
- This repository collects the tool packages used for RNA Editing analysis in the context of the ICGC ARGO project.

### Alternative Promoter Analysis
- WIP git repo: https://github.com/icgc-argo-workflows/alternative-promoter-analysis
- This repository collects the tool packages used for Alternative Promoter analysis in the context of the ICGC ARGO project.

### Allele Specific Expression
- WIP git repo: https://github.com/icgc-argo-workflows/allele-specific-expression
- This repository collects analysis package used for allele specific expression(ASE) in the context of the ICGC ARGO project

### RNA-Seq Splicing
- WIP git repo: https://github.com/icgc-argo-workflows/rna-seq-splicing
- This repository contains the packages for RNA-Seq splicing analysis that are part of the ICGC ARGO data analysis pipeline.

### RNA-Seq Data Simulation
- WIP git repo: https://github.com/icgc-argo-workflows/rna-seq-data-simulation
- This repository contains code for the generation of simulated RNA-Seq reads that can be used for the benchmarking of different parts of the ICGC ARGO RNA-Seq analysis pipeline.


## ARGO QC Tools and Workflows
- WIP git repo: https://github.com/icgc-argo-workflows/argo-qc-tools
- This repository contains a collection of data QC tools/modules used in various ICGC ARGO workflows


## Mutational Signatures Analysis
- WIP git repo: https://github.com/icgc-argo-workflows/icgc-argo-mutational-signatures
- This repository contains a collection of analysis packages that are part of the ICGC ARGO mutational signatures pipeline.


## ARGO Reference Files
- WIP git repo: https://github.com/icgc-argo-workflows/argo-reference-files
- This repository contains urls and metadata for all reference files used by the ICGC-ARGO data analysis pipelines


## ARGO Utility
- Metadata payload generation tools: https://github.com/icgc-argo-workflows/data-processing-utility-tools
- Song/Score download/upload tools: https://github.com/icgc-argo-workflows/nextflow-dna-seq-processing-tools
- Quality control/benchmarking metrics collecting tools: https://github.com/icgc-argo-workflows/data-qc-tools-and-wfs
- DNA-Seq data processing tools: https://github.com/icgc-argo-workflows/dna-seq-processing-tools
- Genomic variant calling tools: https://github.com/icgc-argo-workflows/variant-calling-tools
- Dockerized GATK tools: https://github.com/icgc-argo-workflows/gatk-tools
- Benchmark datasets: https://github.com/icgc-argo-workflows/metadata-for-benchmarking-datasets
- Workflow migration tool: https://github.com/icgc-argo-workflows/workflow-repo-migration
