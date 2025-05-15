# Biol-668-Final-Project

# Overview
This Snakemake pipeline automates the process of assembling and polishing of phage genomes from Illumina sequencing reads.

The workflow performs the following steps for each sample:

1. **Quality Control** of raw reads using FastQC
2. **Adapter and contaminant trimming** using BBDuk
3. **Subsampling** with seqtk
4. **Genome assembly** using SPAdes
5. **Read mapping and polishing** using BBMap + Pilon
6. **BLASTn search** for the closest known phage genome
7. **NCBI reference genome download** using efetch
8. **Genome reordering** using RagTag (if needed)
9. **Final polishing** and cleanup
10. **Raw reads and outputs moved** to sample-specific directories
