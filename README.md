---

# Genomics & Bioinformatics Pipeline Projects – Hands-on Practice with AWS Batch, Nextflow & Docker

---

## **1️⃣ [WES Structural & CNV Analysis Pipeline (AWS Batch)](https://github.com/Dinakaran1998/WES-Structural-CNV-Analysis-Pipeline-on-AWS-Batch)**

GitHub: [https://github.com/Dinakaran1998/WES-Structural-CNV-Analysis-Pipeline-on-AWS-Batch](https://github.com/Dinakaran1998/WES-Structural-CNV-Analysis-Pipeline-on-AWS-Batch)

WES pipeline for alignment, CNV, and structural variant detection.

**Tech:** Nextflow, AWS Batch, Docker, BWA, GATK, Manta, S3, EFS.

Align FASTQ → mark duplicates → CNV calling → SV detection.

Containerized workflows with all dependencies inside images.

Reference genome & BED intervals staged from S3/EFS.

---
## **2️⃣ [Variant ACMG Classifier](https://github.com/Dinakaran1998/variant_oncogenicity_classifier)**

GitHub: [https://github.com/Dinakaran1998/variant_oncogenicity_classifier](https://github.com/Dinakaran1998/variant_oncogenicity_classifier)

Classifies genomic variants using ACMG/AMP guidelines.

**Tech:** Python 3.8+, Polars, PyArrow, multi-threading.

Input: Parquet variant file; Output: annotated CSV with classification.

Supports large datasets efficiently (~25× faster than Pandas).

Uses lookup tables for protein domains, hotspots, population frequency.



---

## **3️⃣ [RNA-seq Fusion Detection Pipeline (AWS Batch)](https://github.com/Dinakaran1998/RNA-seq-Fusion-Detection-Pipeline-on-AWS-Batch)**

GitHub: [https://github.com/Dinakaran1998/RNA-seq-Fusion-Detection-Pipeline-on-AWS-Batch](https://github.com/Dinakaran1998/RNA-seq-Fusion-Detection-Pipeline-on-AWS-Batch)

Detects gene fusions from RNA-seq using STAR & Arriba.

**Tech:** Nextflow, AWS Batch, Docker, STAR, Arriba, SAMtools, S3, EFS.

Align FASTQ → STAR sorted BAM → Arriba fusion detection.

References stored on EFS for shared access across nodes.

Outputs fusion reports and BAM files to S3.

---

## **4️⃣ [RNA-seq Expression Pipeline (Nextflow + STAR + featureCounts)](https://github.com/Dinakaran1998/Nextflow-RNAseq-pipeline)**

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

## **6️⃣ [MSI & TMB Pipeline (AWS Batch)](https://github.com/Dinakaran1998/MSI_TMB)**

GitHub: [https://github.com/Dinakaran1998/MSI_TMB](https://github.com/Dinakaran1998/MSI_TMB)

Calculates microsatellite instability & tumor mutational burden.

**Tech:** Nextflow, AWS Batch, Docker, msisensor-pro, Python, S3.

Input: BAM/VCF from WES/WGS; Output: MSI & TMB reports.

Processes run independently per sample; outputs staged to S3.

Parallel execution via EC2 compute environment for scalability.

---

## **7️⃣ [FastQC Pipeline (AWS Batch)](https://github.com/Dinakaran1998/fastqc)**

GitHub: [https://github.com/Dinakaran1998/fastqc](https://github.com/Dinakaran1998/fastqc)

Performs quality control on FASTQ sequencing files.

**Tech:** Nextflow, FastQC, Docker, AWS Batch, S3, EC2.

Generates QC reports highlighting quality, adapter contamination, GC content.

Containerized with AWS CLI for S3 staging.

Scalable execution across EC2 instances.

---

## **8️⃣ [Pharmacogenomics (PGx) Pipeline (AWS Batch)](https://github.com/Dinakaran1998/Nextflow-PGX)**

GitHub: [https://github.com/Dinakaran1998/Nextflow-PGX](https://github.com/Dinakaran1998/Nextflow-PGX)

Generates PGx reports from VCF files for drug response analysis.

**Tech:** Nextflow, Docker, PharmCAT, AWS Batch, EC2, S3.

Annotates pharmacogenes (CYPs, HLA, TPMT, SLCO1B1) per sample.

Supports WES/WGS, RNA-seq, scRNA-seq input VCFs.
Reports staged to S3 automatically; container includes AWS CLI.

---

# ☁️ AWS Glue, EMR & Hail Projects – Scalable Genomic Data Processing

---

### 🧩 **1️⃣ AWS Glue – DataFrame Benchmarking**

🔗 **GitHub:** [https://github.com/Dinakaran1998/AWS-Glue-Job-Benchmarking-DataFrame-Libraries-for-Genomic-Data](https://github.com/Dinakaran1998/AWS-Glue-Job-Benchmarking-DataFrame-Libraries-for-Genomic-Data)

**About:**
Benchmarked six Python DataFrame engines — **Pandas, FireDucks, Dask, Polars, DuckDB, and PySpark** — for large-scale genomic variant aggregation on AWS Glue. The objective was to identify the fastest and most scalable engine for bioinformatics workloads.
**Result:** 🥇 **Polars** achieved the best performance, completing the aggregation in **~7 seconds**, significantly outperforming PySpark (43 s) and others.

**Tech Used:**
AWS Glue 4.0, Python 3.10, S3, Pandas, Dask, Polars, DuckDB, PySpark, FireDucks

---

### 🧩 **2️⃣ AWS Glue – Variant Count by Chromosome**

🔗 **GitHub:** [https://github.com/Dinakaran1998/variant_count_aws_glue](https://github.com/Dinakaran1998/variant_count_aws_glue)

**About:**
ETL job that aggregates variant counts per chromosome from Parquet files stored in S3. Produces concise variant summaries for genomic reporting and visualization pipelines.

**Tech Used:**
AWS Glue 4.0, Apache Spark, Python, Amazon S3

---

### 🧩 **3️⃣ AWS EMR – Split Variants by Chromosome**

🔗 **GitHub:** [https://github.com/Dinakaran1998/AWS-EMR-Job-Split-Variants-by-Chromosome](https://github.com/Dinakaran1998/AWS-EMR-Job-Split-Variants-by-Chromosome)

**About:**
Spark-based EMR job that reads large genomic CSV files and splits them into **individual Parquet files per chromosome**, optimizing data retrieval and downstream Spark performance.

**Tech Used:**
AWS EMR 6.15.0, Apache Spark, Python, Amazon S3

---

### 🧩 **4️⃣ AWS Glue – CSV to Parquet Conversion**

🔗 **GitHub:** [https://github.com/Dinakaran1998/csv_to_parquet_genomic_data_aws_glue](https://github.com/Dinakaran1998/csv_to_parquet_genomic_data_aws_glue)

**About:**
Converts multiple CSV variant datasets into **partitioned Parquet** format by chromosome. Designed for scalable storage, faster queries, and schema inference in genomic ETL pipelines.

**Tech Used:**
AWS Glue 4.0, Apache Spark, Python, Amazon S3

---

### 🧩 **5️⃣ AWS EMR – Variant Count by Chromosome**

🔗 **GitHub:** [https://github.com/Dinakaran1998/AWS-EMR-Job-Count-Variants-by-Chromosome](https://github.com/Dinakaran1998/AWS-EMR-Job-Count-Variants-by-Chromosome)

**About:**
Distributed Spark job on EMR that counts variants per chromosome from Parquet datasets. Enables high-throughput genomic analytics for medium to large-scale data (1–50 GB).

**Tech Used:**
AWS EMR, Apache Spark, Python, Amazon S3

---

### 🧩 **6️⃣ Hail – VCF to CSV Transformation**

🔗 **GitHub:** [https://github.com/Dinakaran1998/-Hail-Variant-Transformation-Pipeline-VCF-to-CSV](https://github.com/Dinakaran1998/-Hail-Variant-Transformation-Pipeline-VCF-to-CSV)

**About:**
Performs large-scale genomic variant transformation from **VCF/VCF.BGZ** files to tabular CSV format using **Hail**, a distributed framework built on Apache Spark. Ideal for variant-level downstream analysis.

**Tech Used:**
Hail, Apache Spark, Python 3.8+, GRCh38 Reference Genome

---




