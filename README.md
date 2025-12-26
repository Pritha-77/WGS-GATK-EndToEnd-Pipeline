# WGS-GATK-EndToEnd-Pipeline

An end-to-end **Whole Genome Sequencing (WGS) analysis pipeline** based on **GATK Best Practices**, covering raw FASTQ quality control to variant calling, joint genotyping, annotation, QC reporting, and genome browser visualization.

This pipeline is suitable for **single-sample and multi-sample (cohort) WGS analysis** and is designed for **research, thesis work, and reproducible genomics studies**.

---

## 🚀 Features

- Raw FASTQ quality control (FastQC)
- Alignment to reference genome (BWA-MEM)
- Duplicate marking and sorting (SAMtools)
- Base Quality Score Recalibration (BQSR)
- Variant calling using **GATK HaplotypeCaller**
- Single-sample and **joint genotyping (GenomicsDB + GenotypeGVCFs)**
- Variant filtering and statistics
- Variant annotation (snpEff)
- Comprehensive QC summary report
- Genome browser visualization files (BED & coverage tracks)
- Fully bash-based, **no conda required**

---

## 📁 Pipeline Overview

FASTQ -> FastQC -> BWA-MEM alignment -> Sorting & duplicate marking -> BQSR -> HaplotypeCaller (GVCF mode) -> GenotypeGVCFs -> Filtering & QC -> Annotation (snpEff) -> Visualization (IGV/UCSC)


---

## 🛠 Software Requirements

| Tool | Version |
|----|----|
| GATK | ≥ 4.2 |
| Java | OpenJDK 11 |
| BWA | ≥ 0.7 |
| SAMtools | ≥ 1.10 |
| BCFtools | ≥ 1.10 |
| BEDTools | ≥ 2.30 |
| FastQC | ≥ 0.11 |
| snpEff | Latest |

---

## 🔍 Check if required tools are installed

```bash
for tool in gatk bwa samtools bcftools bedtools fastqc bgzip tabix java; do
    if command -v $tool &>/dev/null; then
        echo "✓ $tool found"
    else
        echo "✗ $tool NOT FOUND"
    fi
done
