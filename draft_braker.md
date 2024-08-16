# Genome annotation

## Genome preparation

The first phase of the Ensembl genome annotation pipeline involves loading an assembly into the Ensembl core database schema and then running a series of analyses on the loaded assembly to identify an initial set of genomic features.

### Repeat Elements

After the genomic sequence has been loaded into a database, it is screened for sequence patterns, including repeats, using Red ([Girgis, H.Z., 2015](https://doi.org/10.1186/s12859-015-0654-5)), dustmasker ([Morgulis, A., *et al.*, 2006](https://doi.org/10.1089/cmb.2006.13.1028)), and TRF ([Benson, G., 1999](https://doi.org/10.1093/nar/27.2.573)).

Combined, these tools provide a quick and acqurate identification of repeat elements, low-complexity DNA structures, and tandem repeats, respecfully, as well as a soft-masked version of the genome that will be used for the remaining of the analyses.

### Low complexity features, ab initio predictions

On the soft-masked genome, Transcription Start Sites are predicted using Eponine–scan ([Down, T.A., *et al*, 2002](https://doi.org/10.1101/gr.216102)).
Additionally, CpG islands ([Larsen, F., *et al*, 1992](https://doi.org/10.1016/0888-7543(92)90024-m)) longer than 200 bases are  predicted using the [command line version of CpG Finder](https://genome-source.gi.ucsc.edu/gitlist/kent.git/tree/master/src/utils/cpgIslandExt/) ([Gardiner-Garden, M., *et al*, 1987](https://doi.org/10.1016/0022-2836(87)90689-9)).

These predictions and features are for display purposes only; they are not used in the gene annotation process.

## Protein-coding model generation (BRAKER2 pipeline)

[BRAKER2](https://doi.org/10.1093/nargab/lqaa108) is one of the most popular tools for automatic eukaryotic genome annotation. This pipeline has been included in the Ensembl gene annotation process to generate supplementary gene annotation tracks for non-vertebrate species with an existing Ensembl annotation, or as a draft annotation for species without transcriptomic data.

BRAKER2 includes [GeneMark-ES](https://doi.org/10.1093/nar/gki937), a self-training algorithm for ab initio gene prediction, and [Augustus](https://doi.org/10.1093/bioinformatics/btn013), one of the most accurate gene prediction tools. The tool provides different options according to the available data. In the annotation process the pipeline is used in the default protein mode when the transcriptomic data are not available.

The set of proteins have been downloaded from [UniProt](https://www.uniprot.org/) ([The UniProt Consortium, 2017](https://doi.org/10.1093/nar/gkw1099)) and OrthoDB ([Kriventseva E.K., *et al*, 2019](https://doi.org/10.1093/nar/gky1053)), using clade-specific filters.

## Functional annotation and identification

We use a [transformer model](https://github.com/Ensembl/gene_symbol_transformer) trained in our manually curated set of annotations to deduce the gene funcion from sequence, thus naming the genes to resemble the namings of its closer gene family. Although this should be assumed to be more a funtion indicative, rather than proper naming, as the subtler naming conventions might not be follow strictly.

Finally, a ensembl stable ID will be assign to each annotated feature. When updating an existing annotation, or replacing it with a new assembly version, an extra step will be taken to try and map the old stable IDs to the features, in an attempt to facilitate working with them.

# Appendix

The Ensembl gene set is generated automatically, meaning that gene models are annotated using the Ensembl gene annotation pipelines. The main focus of the pipelines is to generate a conservative set of protein-coding gene models.
