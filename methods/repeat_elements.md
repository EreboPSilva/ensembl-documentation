### Repeat Elements

After the genomic sequence has been loaded into a database, it is screened for sequence patterns including repeats using RepeatMasker [1] (version 4.0.5 with parameters, -nolow -engine "crossmatch"), dustmasker [2] and TRF [3].

The Repbase mammals library was used with RepeatMasker. In addition to the Repbase [4] library, where available, a custom repeat library was used with RepeatMasker. This custom library was created using RepeatModeler [5].