Pipeline
============

InPBcR-SMSAligner
-------------------------------

Instructions for use
~~~~~~~~~~~~~~~~~~~~~~

**① SMSAligner**

 ``$ SMSSligner –p [Workpath] –t [Core number] –s [Start file id] –e [Split file number]``

*Options*

::

  -p [Workpath]
  -t [number]: number of used CPUs
  -s [number]: Start file id
  -e [number]: Split file number

This means the SMSAligner operation mapped files of reads starting from the start id to the end file id to the start file.


**② SMSCA-Assembler**

 ``$ SMSCA-Assembler –l [libraryname] -s [file of spec format] -fastq [fastq file name] [frg]``

*Options*

::

  -l libraryname Name of the library; freeformat text.
  -t threads     Number of threads to use for correction.
  -noclean       Do not clean up after the correction finishes. By default, the temp<libraryname> directory will be removed on successful completion of the correction.
  -s file of spec format

  For example: human.spec

The pipeline will corrected the sequences and output a CA FRG file consisting of a single LIB message to <libraryname>.frg. It will also output the corrected fasta, qual, and fastq sequences (named <libraryname>.fasta, <libraryname>.qual, and <libraryname>.fastq). Finally, it will assemble the data with default parameters.



SMSAligner-SMScorrect-CA
------------------------------------------

Instructions for use
~~~~~~~~~~~~~~~~~~~~~~

**① SMSAligner**

 ``$ SMSpairwise –d [fastq file name] –w [work folder] –c [number of CPUs] –o [output file name]``

*Options*

::

  -d [dataset]: specify deep sequencing dataset file name (FASTQ format)
  -o [output]: specify output file name
  -t [number]: parallel CPU core number in the processing. This number should not exceed the logical CPU core numbers of all machines involved in the calculation
  -w [folder]: work folder where the temporary file was stored. The folder should be enough large storage space. Note: Please be sure that you have enough space in the temporary folder! You need at least the free space twice as the reference sequence file and the dataset file

*Example：*

  ``$ SMSpairwise –d Ecoli –t 16 –o /public/usrs /Xiao/correct/Ecoli/result.m4 –w /public/usrs /Xiao/correct/Ecoli``


**② SMScorrect**

 ``$ SMScorrect –r [Sequences file name (fastq format)] -t [Number of CPUs] –p [number of corrected sequences] -m4 [output file name (m4 format)] -o [output file name]``

*Options*

::

  -c [number]: parallel CPU core number in the processing. This number should not exceed the logical CPU core numbers of all machines involved in the calculation.
  -o [output]: specify output file name.
  -m4 [m4 format]: specify output file name.
  -p [number]: number of corrected sequences in each correction.
  -r [sequence]: specify sequences file name (FASTQ format).

*Example：*

  ``$ SMScorrect –r Ecoli –t 32 –p 200000 –m4 result.m4 –o correctedSequences.fasta``


**③ fasta2fastq**

 ``$ fasta2fastq –A [fasta file name] –Q [fastq file name]``

*Example：*

  ``$ fasta2fastq –A correctedSequences.fasta –Q correctedSequences.fastq``


**④ SMSCA-Assembler**

 ``$ SMSCA-Assembler –l [libraryname] -s [file of spec format] -fastq [fastq file name] [frg]``

*Options*

::

  -l libraryname Name of the library; freeformat text.
  -t threads     Number of threads to use for correction.
  -noclean       Do not clean up after the correction finishes. By default, the temp<libraryname> directory will be removed on successful completion of the correction.
  -s file of spec format

*Example：*

  ``$SMSCA-Assembler –l Ecoli –s Ecoli.spec –pbCNS –fastq correctedSequences.fastq genomesize=12000000``












