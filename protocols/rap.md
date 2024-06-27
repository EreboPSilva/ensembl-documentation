# Genome annotation

## Genome preparation

The genome phase of the Ensembl gene annotation pipeline involves loading an assembly into the Ensembl core database schema and then running a series of analyses on the loaded assembly to identify an initial set of genomic features.

The most important aspect of this phase is identifying repeat features (primarily through RepeatMasker) as soft masking of the genome is used extensively later in the annotation process.
### Repeat Elements

After the genomic sequence has been loaded into a database, it is screened for sequence patterns, including repeats using Red ([Girgis, H.Z., 2015](https://doi.org/10.1186/s12859-015-0654-5)), dustmasker ([Morgulis, A., *et al.*, 2006](https://doi.org/10.1089/cmb.2006.13.1028)) and TRF ([Benson, G., 1999](https://doi.org/10.1093/nar/27.2.573)).
### Low complexity features, ab initio predictions

On the softmasked genome, transcription start sites are predicted using Eponine–scan ([Down, T.A., *et al*, 2002](https://doi.org/10.1101/gr.216102)). Additionally, CpG islands ([Larsen, F., *et al*, 1992](https://doi.org/10.1016/0888-7543(92)90024-m))longer than 400 bases are also predicted using the  and tRNAs are also predicted. The results of Eponine-scan, CpG[7], and tRNAscan [8] are for display purposes only; they are not used in the gene annotation process.

Genscan [9] is run across repeat-masked sequence to identify ab initio gene predictions. Genscan predictions are for display purposes only and are not used in the model generation phase.

Lastly, transport RNAs are predicted using tRNAscan-SE ([Chan, P.P., *et al*, 2019](https://doi.org/10.1007/978-1-4939-9173-0_1)).## Projection-base gene model generation

...
## Homology-base gene model prediction

...
## Transcriptomic-base gene model generation
## Filtering gene models and finalization of gene set
