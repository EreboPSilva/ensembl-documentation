## Filtering Gene Models and Finalisation of Gene Set

### Prioritising models at each locus

Low quality models are removed, and data is collapsed and consolidated into a final set of gene models plus their associated non-redundant transcripts. When collapsing the data, priority is given to models derived from transcriptomic data; where RNA-seq data is fragmented or missing, homology data takes precedence.

### Addition of UTR to coding models
The set of coding models is extended into the untranslated regions (UTRs) using RNA-seq data (if available). The criterion for adding UTR from RNA-seq alignments to protein models lacking UTR (such as the protein-to-genome alignment models) is that the intron coordinates from the model missing UTR exactly match a subset of the coordinates from the UTR donor model.


