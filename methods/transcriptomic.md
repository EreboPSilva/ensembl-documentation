### Model Generation Through Alignment of Transcriptomic Data to the Genome

#### Aligning RNASeq Data
Where available, RNA-seq data are downloaded from [ENA](https://www.ebi.ac.uk/ena/) and utilised for annotation. The obtained reads are aligned to the genome using STAR ([Dobin A., *et al*, 2013](https://doi.org/10.1093/bioinformatics/bts635)) and models assembled using Scallop ([Shao M., Kingsford C., 2017](https://doi.org/10.1038/nbt.4020)).

#### Aligning Long-read Transcriptomic Data
Where available, long-read transcriptomic data (PacBio IsoSeq or Oxford Nanopore) are downloaded from [ENA](https://www.ebi.ac.uk/ena/) and used in the annotation process. The long-read data are mapped to the genome using Minimap2 ([Li H., 2018](https://doi.org/10.1093/bioinformatics/bty191)) with the recommended settings for Iso-Seq and Nanopore data.

#### Validating Protein-coding Models
Protein-coding models are validated by aligning the longest ORF against a database of eukaryotic UniProt proteins using Diamond ([Buchfink B., *et al.*, 2021](https://doi.org/10.1038/s41592-021-01101-x)). If the alignments are insufficient, additional validation is performed using RNASamba ([Camargo A.P., *et al*, 2020](https://doi.org/10.1093/nargab/lqz024)) and CPC2 ([Kang Y., *et al.*, 2017](https://doi.org/10.1093/nar/gkx428)).
