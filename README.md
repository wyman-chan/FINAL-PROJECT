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
