## Repeat Finding

After the genomic sequence has been loaded into a database, it is screened for sequence patterns including repeats using RepeatMasker [1], (version 4.0.5 with parameters -nolow -engine "RMBlast"), dustmasker [2] and TRF [3]. In addition to the Repbase [4] library, where available, a custom repeat library is used with RepeatMasker. Custom libraries are created using RepeatModeler2 [5] and can be downloaded via thre [Ensembl FTP](https://ftp.ebi.ac.uk/pub/databases/ensembl/repeats/unfiltered_repeatmodeler/species/).
