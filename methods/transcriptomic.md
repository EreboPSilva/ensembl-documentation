## Model generation through alignment of transcriptomic data to the genome

### Aligning RNASeq Data
Where available, RNA-seq data are downloaded from [ENA](https://www.ebi.ac.uk/ena/) and utilised for annotation. The obtained reads are aligned to the genome using STAR ([Dobin A., *et al*, 2013](https://academic.oup.com/bioinformatics/article/29/1/15/272537?login=true)) and models assembled using Scallop ([Shao M., Kingsford C., 2017](https://www.nature.com/articles/nbt.4020)). 

### Aligning Long-read Transcriptomic Data
Where available, long-read transcriptomic data (PacBio IsoSeq or Oxford Nanopore) are downloaded from [ENA](https://www.ebi.ac.uk/ena/) and used in the annotation process. The long-read data are mapped to the genome using Minimap2 ([Li H., 2018](https://academic.oup.com/bioinformatics/article/34/18/3094/4994778)) with the recommended settings for Iso-Seq and Nanopore data. 

### Validating Protein-coding Models
Protein-coding models are validated by aligning the longest ORF against a database of eukaryotic UniProt proteins using Diamond ([Buchfink B., Reuter K., Drost HG., 2021](https://www.nature.com/articles/s41592-021-01101-x)). If the alignments are insufficient, additional validation is performed using RNASamba ([Camargo A.P., *et al*, 2020](https://academic.oup.com/nargab/article/2/1/lqz024/5701461)) and CPC2 ([Kang Y., 2017](https://academic.oup.com/nar/article/45/W1/W12/3831091)).
