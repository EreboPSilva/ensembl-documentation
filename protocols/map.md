# Genome annotation

## Genome preparation

The genome phase of the Ensembl gene annotation pipeline involves loading an assembly into the Ensembl core database schema and then running a series of analyses on the loaded assembly to identify an initial set of genomic features.

The most important aspect of this phase is identifying repeat features (primarily through RepeatMasker) as soft masking of the genome is used extensively later in the annotation process.
### Repeat Elements

After the genomic sequence has been loaded into a database, it is screened for sequence patterns including repeats using RepeatMasker [1] (version 4.0.5 with parameters, -nolow -engine "crossmatch"), dustmasker [2] and TRF [3].

The Repbase mammals library was used with RepeatMasker. In addition to the Repbase [4] library, where available, a custom repeat library was used with RepeatMasker. This custom library was created using RepeatModeler [5].
### Low complexity features, ab initio predictions

Transcription start sites are predicted using Eponine–scan [6]. CpG islands longer than 400 bases and tRNAs are also predicted. The results of Eponine-scan, CpG[7], and tRNAscan [8] are for display purposes only; they are not used in the gene annotation process.

Genscan [9] is run across repeat-masked sequence to identify ab initio gene predictions. Genscan predictions are for display purposes only and are not used in the model generation phase.
## Projection-base gene model generation

...
## Homology-base gene model prediction

...
## Transcriptomic-base gene model generation
## Filtering gene models and finalization of gene set
### Pseudogenes

Test.
