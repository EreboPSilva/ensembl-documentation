# Genome annotation

## Genome preparation

The genome preparation phase of the Ensembl gene annotation system involves loading an assembly into an Ensembl core database schema and then running a series of analyses on the loaded assembly to identify an initial set of genomic features.

The most important aspect of this phase is identifying repeat features as soft masking of the genome is used extensively later in the annotation process.

### Repeat Finding

After the genomic sequence has been loaded into a database, it is screened for sequence patterns, including repeats using Red ([Girgis, H.Z., 2015](https://doi.org/10.1186/s12859-015-0654-5)), dustmasker ([Morgulis, A., *et al.*, 2006](https://doi.org/10.1089/cmb.2006.13.1028)) and TRF ([Benson, G., 1999](https://doi.org/10.1093/nar/27.2.573)).

### Low Complexity Feature Prediction

Transcription start sites are predicted using Eponine–scan [6], CpG islands longer than 400 bases are predicted using CpG ([Larsen, F., *et al*, 1992](https://doi.org/10.1016/0888-7543(92)90024-m)) and tRNAs are predicted using tRNAscan-SE [Chan, P.P., *et al*, 2019](https://doi.org/10.1007/978-1-4939-9173-0_1). The results of Eponine-scan, CpG, and tRNAscan are for display purposes only; they are not used in the gene annotation process. 

## Model Generation Through the BRAKER2 Annotation Pipeline

[BRAKER2](https://github.com/Gaius-Augustus/BRAKER)([Bruna, T., *et. al* 2021](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7787252/)) is one of the most popular tools for automatic eukaryotic genome annotation. This pipeline has been included in the Ensembl gene annotation process to generate supplementary gene annotation tracks for non-vertebrate species with an existing Ensembl annotation, or as a draft annotation for species without transcriptomic data, for more informaiton, see our [blog post](https://www.ensembl.info/2022/05/24/rapid-release-33-contains-species-annotated-via-braker2/).

BRAKER2 includes [GeneMark-ES](https://genemark.bme.gatech.edu/)([Lomsadze, A., *et. al*, 2005](https://academic.oup.com/nar/article/33/20/6494/1082033)), a self-training algorithm for ab initio gene prediction, and [Augustus](https://bioinf.uni-greifswald.de/augustus/)([Stanke, M., *et. al*, 2006](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC1538822/)), one of the most accurate gene prediction tools. The tool provides different options according to the available data. In the annotation process the pipeline is used in the default protein mode.

The set of proteins have been downloaded from [UniProt](https://www.uniprot.org/) ([The UniProt Consortium, 2017](https://doi.org/10.1093/nar/gkw1099)) and [OrthoDB](https://www.orthodb.org/) ([Kriventseva E.K., *et al*, 2019](https://doi.org/10.1093/nar/gky1053)), using clade-specific filters.

