# Biol-668-Final-Project

# Overview
This Snakemake pipeline automates the process of assembling and polishing of phage genomes from Illumina sequencing reads.

# Contents
SnakeAssembly: Automated pipeline that will perform the following steps for each sample:

  1. **Quality Control** of raw reads using FastQC
  2. **Adapter and contaminant trimming** using BBDuk
  3. **Subsampling** with seqtk
  4. **Genome assembly** using SPAdes
  5. **Read mapping and polishing** using BBMap + Pilon
  6. **BLASTn search** for the closest known phage genome

SnakeInput.yaml: The input file where you will list your the names of your phage reads according to the example.

# Dependencies

| Tool                       | Purpose                                  | Install Source     |
| -------------------------- | ---------------------------------------- | ------------------ |
| `snakemake`                | Workflow management                      | `conda` / `pip`    |
| `fastqc`                   | Quality control of raw and cleaned reads | `bioconda`         |
| `bbmap`                    | Adapter trimming and mapping             | `bioconda`         |
| `seqtk`                    | Subsampling reads                        | `bioconda`         |
| `spades`                   | Genome assembly                          | `bioconda`         |
| `samtools`                 | Manipulating `.sam`/`.bam` files         | `bioconda`         |
| `pilon`                    | Genome polishing                         | `bioconda`         |
| `blastn`                   | Finding closest reference genome         | `bioconda`         |
| `entrez-direct` (`efetch`) | Downloading reference genome from NCBI   | `bioconda`         |
| `ragtag`                   | Reordering genome to match reference     | `bioconda`         |
| `biopython`                | For optional rotation scripting          | `pip` / `bioconda` |

# Quick Start
Clone the repository

`git clone https://github.com/wyman-chan/FINAL-PROJECT.git`

`cd FINAL-PROJECT`


Set up the Conda environment

`conda create -n snakemake_env -c bioconda -c conda-forge snakemake`

`conda activate snakemake_env`


Run the program

`snakemake -s SnakeAssembly`


# Example
FASTQC
![CCF85A0D-837A-43BE-93F0-0B631E4E2B4A_1_105_c](https://github.com/user-attachments/assets/9eb804d1-cb36-48ea-85d9-93eb0d706c31)

SPAdes (Bandage visualization)
![60C46CFE-D7D1-4767-A710-AEB297106723_1_105_c](https://github.com/user-attachments/assets/bfe1256e-ad55-4fde-96f4-428f0ea4ba02)

Blastn (website visualization)
![73096B9C-9AD6-4999-988D-8B4D686EAF02_1_105_c](https://github.com/user-attachments/assets/ecc89bc1-a9a5-4fd5-bd17-029e1c9a1543)

