# Genome annotation

## Genome preparation

The genome preparation phase of the Ensembl gene annotation system involves loading an assembly into an Ensembl core database schema and then running a series of analyses on the loaded assembly to identify an initial set of genomic features.

The most important aspect of this phase is identifying repeat features as soft masking of the genome is used extensively later in the annotation process.

### Repeat Finding

After the genomic sequence has been loaded into a database, it is screened for sequence patterns, including repeats using Red ([Girgis, H.Z., 2015](https://doi.org/10.1186/s12859-015-0654-5)), dustmasker ([Morgulis, A., *et al.*, 2006](https://doi.org/10.1089/cmb.2006.13.1028)) and TRF ([Benson, G., 1999](https://doi.org/10.1093/nar/27.2.573)).

### Low Complexity Feature Prediction

Transcription start sites are predicted using Eponine–scan [6], CpG islands longer than 400 bases are predicted using CpG ([Larsen, F., *et al*, 1992](https://doi.org/10.1016/0888-7543(92)90024-m)) and tRNAs are predicted using tRNAscan-SE [Chan, P.P., *et al*, 2019](https://doi.org/10.1007/978-1-4939-9173-0_1). The results of Eponine-scan, CpG, and tRNAscan are for display purposes only; they are not used in the gene annotation process. 
