# CLC-Genomics
An unofficial repo for CLC Genomics Workflows, custom datasets, tutorials, and other files.

If you are looking for some example workflows for using CLC with SARSCOV2 data - look under the "CLC-SARSCOV2-Workflows" folder. There you will find some downloadable workflows that can be imported, edited, and run in CLC. Have fun!

Also, free Extended Trials of both CLC Genomics ProSuite and Ingenuity Pathway Analysis are available from QIAGEN Digital Insights until June 15th, 2020. Please visit our **[COVID-19 Emergency Response Licenses](https://go.qiagen.com/QDI-COVID19)** page to request your licenses and access additional resources. 

**FOR RESEARCH USE ONLY.**

** The workflows found here are provided AS IS by Jonathan Jacobs, and not officially by QIAGEN Digital Insights. They are intended as examples in the hopes that users may find them useful to get started quickly on analyzing their SARS-CoV-2 genomics data with CLC. If you have any questions - please DM me on Twitter @bioinformer or here on GitHub. **

**DISCLAIMER** [QIAGEN Digital Insights](https://https://digitalinsights.qiagen.com/) provided here are intended for molecular biology applications only. These products are not intended for the diagnosis, prevention or treatment of a disease. For up-to-date licensing information and product-specific disclaimers, see the respective QIAGEN kit handbook or user manual. QIAGEN kit handbooks and user manuals are available at (www.qiagen.com) or can be requested from QIAGEN Technical Services or your local distributor.


# **CLC Genomics Workbench Workflows for SARS-CoV-2**
## **Background**
The zip archives available here are intended to provide [CLC Genomics Workbench](https://digitalinsights.qiagen.com/products-overview/discovery-insights-portfolio/analysis-and-visualization/qiagen-clc-genomics-workbench/) users with a quick way to get started with analysis of SARS-CoV-2 genomics data from a variety of upstream laboratory protocols. Each workflow includes - a minimum - qc, trim, mapping, variant calling and the output of a consensus sequence. To the best of my ability, I have created these workflows to take into account aspects of the wet-lab protocols \(where ever possible), and may include specific primer sequences, adapter sequences, or other parameter settings to account for differences in sequencing platforms\(i.e. Illumina vs. Ion Torrent data).  

Please contact me via email \(jonathan.jacobs@qiagen.com) or Twitter \([\@bioinformer](https://twitter.com/bioinformer)) if there's any major issue with any of these pipelines that need to be fixed.

## USAGE
Simply download the .zip archives provides above and import them into CLC Genomics Workbench using the Import->Standard Import option on the tool bar. The zip archive will be automatically unzipped and the workflows can be open, edited, run directly, or installed for other users on the same system.

## Workflows
### QIAseq SARSCOV2 Panel 
https://github.com/jonathanjacobs/CLC-Genomics/blob/master/CLC-SARSCOV2-Workflows/QIAseq%20SARSCOV2%20Workflow.2.zip

This zip file contains three workflows for CLC Genomics Workbench that are designed to work with QIAGEN's QIAseq SARSCOV2 amplicon sequencing panel. The workflows include a basic qc/mapping/consensus calling workflow; an advanced workflow that extends the basic workflow to include indel, structural variant calling, local realignment of potential indel regions, and a low frequency variant detection step; and a simple fast multiple sequence alignment and neighbor-joining tree building workflow. There many other ways to build trees in CLC Genomics Workbench for this purpose, and other "good" ways to build SARS-CoV-2 phylo trees would be to use a NJ tree as a starting guide to then run maximum likelihood estimation tree and/or use read mapping data to build SNP based trees of all samples. 

### ARTICv3 SARSCOV2 Workflows
https://github.com/jonathanjacobs/CLC-Genomics/blob/master/CLC-SARSCOV2-Workflows/SARSCOV2%20ARTICv3.zip

This zip archive includes workflows intended for both Illumina and Nanopore data produced from the ARTICv3 protocol. The nanopore workflows use an implemetation in CLC of minimap2/racon included with CLC Genomics Workbench - and not Medaka, which is being used by several other labs. Variant calling is done with CLC using our Low Frequency Variant Calling with relatively leanient settings "inspired by" those in the  Medaka pipeline, but care should be taken in evaluating variants or quasispecies results. Also, position specific primer trimming, primer/dimers, and chimera filtering is included, similar to [Nick Loman's pipeline](https://artic.network/ncov-2019), but the results may nonetheless have some differences. 

### Ion AmpliSeq SARSCOV2 Workflows
https://github.com/jonathanjacobs/CLC-Genomics/blob/master/CLC-SARSCOV2-Workflows/ThermoFisher%20AmpliSeq%20SARSCOV2%20v3.1.zip

This zip contains an implementation of a CLC Genomics Workbench workflow suitable for use with ThermoFisher Ion AmpliSeq SARSCOV2 panel data. Due to the way TF AmpliSeq data is generated, no primer BED file is provided. However, if users have access to the bed file for this workflow, this can be included into the workflow immediately after read mapping, but adding our "Trim Primers & Dimers" tool. UPDATED to include a multiple sequence alignment and maximum likelihood tree workflow, and an optional direct BAM import workflow for those who don't want to first import data to CLC prior to running the workflow.

### SARCOV2_Swift_Illumina
https://github.com/jonathanjacobs/CLC-Genomics/blob/master/CLC-SARSCOV2-Workflows/SARCOV2_Swift_Illumina-2.0.zip

The SARCOV2_Swift_Illumina-2.0.cpw workflow has been contributed by Gonzalo Manrique <grmanrique@fcien.edu.uy>. It is compatible with CLC Genomics Workbench v20 or newer, and is provided as is without warrenty. Please contact QIAGEN Digital Insights for support questions related to CLC Genomics Workbench. For questions related to this workflow specifically, please contact Gonzalo Manrique <grmanrique@fcien.edu.uy>.

## Requirements
All the workflows included above were built with [CLC Genomics Workbench v20](https://digitalinsights.qiagen.com/products-overview/discovery-insights-portfolio/analysis-and-visualization/qiagen-clc-genomics-workbench/) with several additional \(free) plugins installed, including:  Biomedical Genomics Analysis plugin, the Long Read Analysis plugin, and the Whole Genome Alignment plugin. These workflows may not run with prior versions of CLC Genomics Workbench.

## Licensing
[CLC Genomics Workbench](https://digitalinsights.qiagen.com/products-overview/discovery-insights-portfolio/analysis-and-visualization/qiagen-clc-genomics-workbench/) is a commercial bioinformatics software platform that requires an annual subscription license to use. Limited duration evaluation licenses are available by request from [QIAGEN Digital Insights](https://digitalinsights.qiagen.com/products-overview/discovery-insights-portfolio/analysis-and-visualization/qiagen-clc-genomics-workbench/). Please refer to the [End User License Agreement](https://digitalinsights.qiagen.com/eula/) for CLC Genomics Workbench for additional details.

The workflows provided here are provided "as is" under a Creative Commons Attribution Share Alike 4.0 International license.
