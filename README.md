---

# Genomics & Bioinformatics Pipeline Projects – Hands-on Practice with AWS Batch, Nextflow & Docker

---

**1️⃣ [WES Structural & CNV Analysis Pipeline (AWS Batch)](https://github.com/Dinakaran1998/WES-Structural-CNV-Analysis-Pipeline-on-AWS-Batch)**

GitHub: [https://github.com/Dinakaran1998/WES-Structural-CNV-Analysis-Pipeline-on-AWS-Batch](https://github.com/Dinakaran1998/WES-Structural-CNV-Analysis-Pipeline-on-AWS-Batch)

WES pipeline for alignment, CNV, and structural variant detection.

**Tech:** Nextflow, AWS Batch, Docker, BWA, GATK, Manta, S3, EFS.

Align FASTQ → mark duplicates → CNV calling → SV detection.

Containerized workflows with all dependencies inside images.

Reference genome & BED intervals staged from S3/EFS.

---

**2️⃣ [Variant ACMG Classifier](https://github.com/Dinakaran1998/variant_oncogenicity_classifier)**
GitHub: [https://github.com/Dinakaran1998/variant_oncogenicity_classifier](https://github.com/Dinakaran1998/variant_oncogenicity_classifier)
Classifies genomic variants using ACMG/AMP guidelines.
**Tech:** Python 3.8+, Polars, PyArrow, multi-threading.
Input: Parquet variant file; Output: annotated CSV with classification.
Supports large datasets efficiently (~25× faster than Pandas).
Uses lookup tables for protein domains, hotspots, population frequency.

---

**3️⃣ [RNA-seq Fusion Detection Pipeline (AWS Batch)](https://github.com/Dinakaran1998/RNA-seq-Fusion-Detection-Pipeline-on-AWS-Batch)**
GitHub: [https://github.com/Dinakaran1998/RNA-seq-Fusion-Detection-Pipeline-on-AWS-Batch](https://github.com/Dinakaran1998/RNA-seq-Fusion-Detection-Pipeline-on-AWS-Batch)
Detects gene fusions from RNA-seq using STAR & Arriba.
**Tech:** Nextflow, AWS Batch, Docker, STAR, Arriba, SAMtools, S3, EFS.
Align FASTQ → STAR sorted BAM → Arriba fusion detection.
References stored on EFS for shared access across nodes.
Outputs fusion reports and BAM files to S3.

---

**4️⃣ [RNA-seq Expression Pipeline (Nextflow + STAR + featureCounts)](https://github.com/Dinakaran1998/Nextflow-RNAseq-pipeline)**
GitHub: [https://github.com/Dinakaran1998/Nextflow-RNAseq-pipeline](https://github.com/Dinakaran1998/Nextflow-RNAseq-pipeline)
Aligns RNA-seq reads and quantifies gene expression.
**Tech:** Nextflow, STAR, featureCounts, AWS Batch, Docker, EFS.
Input: paired/single-end FASTQ; Output: sorted BAM & gene counts.
STAR genome indices on EFS for scalable multi-node processing.
Multi-stage Docker builds include AWS CLI and required libs.

---

**5️⃣ [WES/WGS Variant Calling Pipeline (DeepVariant, AWS Batch)](https://github.com/Dinakaran1998/nextflow-WES)**
GitHub: [https://github.com/Dinakaran1998/nextflow-WES](https://github.com/Dinakaran1998/nextflow-WES)
Automates SNP & Indel calling from WES/WGS DNA sequencing.
**Tech:** Nextflow, DeepVariant, BWA, GATK, Docker, AWS Batch, S3.
Workflow: FASTQ → BAM → MarkDuplicates → VCF/gVCF.
Reference genome & dbSNP files staged from EFS.
Parallelized across samples in AWS Batch compute environment.

---

**6️⃣ [MSI & TMB Pipeline (AWS Batch)](https://github.com/Dinakaran1998/MSI_TMB)**
GitHub: [https://github.com/Dinakaran1998/MSI_TMB](https://github.com/Dinakaran1998/MSI_TMB)
Calculates microsatellite instability & tumor mutational burden.
**Tech:** Nextflow, AWS Batch, Docker, msisensor-pro, Python, S3.
Input: BAM/VCF from WES/WGS; Output: MSI & TMB reports.
Processes run independently per sample; outputs staged to S3.
Parallel execution via EC2 compute environment for scalability.

---

**7️⃣ [FastQC Pipeline (AWS Batch)](https://github.com/Dinakaran1998/fastqc)**
GitHub: [https://github.com/Dinakaran1998/fastqc](https://github.com/Dinakaran1998/fastqc)
Performs quality control on FASTQ sequencing files.
**Tech:** Nextflow, FastQC, Docker, AWS Batch, S3, EC2.
Generates QC reports highlighting quality, adapter contamination, GC content.
Containerized with AWS CLI for S3 staging.
Scalable execution across EC2 instances.

---

**8️⃣ [Pharmacogenomics (PGx) Pipeline (AWS Batch)](https://github.com/Dinakaran1998/Nextflow-PGX)**
GitHub: [https://github.com/Dinakaran1998/Nextflow-PGX](https://github.com/Dinakaran1998/Nextflow-PGX)
Generates PGx reports from VCF files for drug response analysis.
**Tech:** Nextflow, Docker, PharmCAT, AWS Batch, EC2, S3.
Annotates pharmacogenes (CYPs, HLA, TPMT, SLCO1B1) per sample.
Supports WES/WGS, RNA-seq, scRNA-seq input VCFs.
Reports staged to S3 automatically; container includes AWS CLI.

---

