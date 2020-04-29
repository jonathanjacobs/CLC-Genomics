# **CLC Genomics Workbench Workflows for SARS-CoV-2**

Last Updated 29-APR-2020

**FOR RESEARCH USE ONLY.**

[QIAGEN Digital Insights](https://https://digitalinsights.qiagen.com/) provided here are intended for molecular biology applications. These products are not intended for the diagnosis, prevention or treatment of a disease. For up-to-date licensing information and product-specific disclaimers, see the respective QIAGEN kit handbook or user manual. QIAGEN kit handbooks and user manuals are available at (www.qiagen.com) or can be requested from QIAGEN Technical Services or your local distributor.

For questions related to the workflows provided here, please contact @jonathanjacobs. 


## **Background**
The zip archives available here are intended to provide CLC Genomics Workbench users with a quick way to get started with analysis of SARS-CoV-2 genomics data from a variety of upstream laboratory protocols. Each workflow includes - a minimum - qc, trim, mapping, variant calling and the output of a consensus sequence. To the best of my ability, I have created these workflows to take into account aspects of the wet-lab protocols \(where ever possible), and may include specific primer sequences, adapter sequences, or other parameter settings to account for differences in sequencing platforms\(i.e. Illumina vs. Ion Torrent data).  

Please contact me via email \(jonathan.jacobs@qiagen.com) or Twitter \([\@bioinformer](https://twitter.com/bioinformer)) if there's any major issue with any of these pipelines that need to be fixed.

## Workflows
###QIAseq SARSCOV2 Panel
This zip file contains three workflows for CLC Genomics Workbench that are designed to work with QIAGEN's QIAseq SARSCOV2 amplicon sequencing panel. The workflows include a basic qc/mapping/consensus calling workflow; an advanced workflow that extends the basic workflow to include indel, structural variant calling, local realignment of potential indel regions, and a low frequency variant detection step; and a simple fast multiple sequence alignment and neighbor-joining tree building workflow. There many other ways to build trees in CLC Genomics Workbench for this purpose, and other "good" ways to build SARS-CoV-2 phylo trees would be to use a NJ tree as a starting guide to then run maximum likelihood estimation tree and/or use read mapping data to build SNP based trees of all samples. 

### ARTICv3 SARSCOV2 Workflows
This zip archive includes workflows intended for both Illumina and Nanopore data produced from the ARTICv3 protocol. The nanopore workflows use an implemetation in CLC of minimap2/racon included with CLC Genomics Workbench - and not Medaka, which is being used by several other labs. Variant calling is done with CLC using our Low Frequency Variant Calling with relatively leanient settings "inspired by" those in the  Medaka pipeline, but care should be taken in evaluating variants or quasispecies results. Also, position specific primer trimming is included as a post-mapping step, similar to Josh Quick's pipeline, but since our tools also include filtering of chimeras and amplicons stemming from primer/dimers - the results may be different than what you would find with Medaka or other FOSS pipelines.

### Ion AmpliSeq SARSCOV2 Workflows
This zip contains an implementation of a CLC Genomics Workbench workflow suitable for use with ThermoFisher Ion AmpliSeq SARSCOV2 panel data. Due to the way TF AmpliSeq data is generated, no primer BED file is provided. However, if users have access to the bed file for this workflow, this can be included into the workflow immediately after read mapping, but adding our "Trim Primers & Dimers" tool. 

## REQUIREMENTS
All the workflows included above were built with CLC Genomics Workbench v20 with several additional \(free) plugins installed, including:  Biomedical Genomics Analysis plugin, the Long Read Analysis plugin, and the Whole Genome Alignment plugin. These workflows may not run with prior versions of CLC Genomics Workbench.

