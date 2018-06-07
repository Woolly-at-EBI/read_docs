# Module 4: Annotated sequence spreadsheet submissions

## Introduction

Annotated sequences (e.g. 16S rRNA genes) can be submitted to the European Nucleotide Archive (ENA) 
as tab-separated (tsv) spreadsheets using the [Webin command line submission interface](cli_01.html) 
with `-context sequence` option. 
 
An annotated sequence submission consists of:
- General sequence information
   - Study accession or unique name (alias)
   - Unique name for the submission
- Sequences
- Functional annotation

The following picture illustrates the stages of the annotated sequence spreadsheet submission process:

![Submission process](images/webin-cli_02.png)

## Stage 1: Pre-register study

Each submission must be associated with a pre-registered study. The study  
accession or unique name (alias) is provided in an `info` file associated 
with the submission. 

Instructions for interactive submitters:
- [Register a Study](mod_02.html)

Instructions for programmatic submitters:
- [Register a Study](prog_02.html)

## Stage 2: Prepare the files

The set of files that are part of the submission are specified using a manifest file.
The manifest file is specified using the `-manifest <filename>` option.

An annotated sequence spreadsheet submission consists of the following files:

- 1 manifest file
- 1 info file
- 1 tab-separated (tsv) spreadsheet containing the sequences and functional annotation

### Sequence names

Sequences must be uniquely numbered in the ENTRYNUMBER column starting from 1.

### Manifest file

The manifest file has two columns separated by a tab (or any whitespace characters):
- File type (first column): case insensitive file type   
- File path (second column): the path to the file

The following case-insensitive file types are supported for annotated sequence spreadsheet submissions:

- INFO: assembly info file
- TAB: tab-separated (tsv) spreadsheet containing the sequences and functional annotation 

For example, the following manifest file represents one submission:

```
INFO    sequences.info.gz
TAB    sequences.tsv.gz
``` 

### Info file

The info file is a text file (USASCII7) containing information common to all sequences.

The file has two columns separated by a tab (or any whitespace characters):
- Field name (first column)
- Field value (second column)

The following fields must be provided:
- STUDY: Study accession or unique name (alias)
- NAME: Unique name for the submission 

An example of an info file:

```
STUDY   TODO
NAME   TODO
```

### Tab-separated (tsv) spreadsheet

Please download and fill an empty tab-separated (tsv) spreadsheet template
from [Interactive Webin](https://www.ebi.ac.uk/ena/submit/sra/): 

- Step 1: Choose 'submit other assembled and annotated sequences' option and click 'Next'.

![Download empty template file_step_1](images/webin_submit_annotated_sequences_01.png)

- Step 2: Select the study for your sequences and click 'Next'.

![Download empty template file_step_2](images/webin_submit_annotated_sequences_02.png)

- Step 3: Click 'Select Checklist' option.

![Download empty template file_step_3](images/webin_submit_annotated_sequences_03.png)

- Step 4: Choose the checklist and  click 'Next'.

![Download empty template file_step_4](images/webin_submit_annotated_sequences_04.png)

- Step 5: Choose the checklist fields and click 'Download Template Spreadsheet'.

![Download empty template file_step_5](images/webin_submit_annotated_sequences_05.png)

## Stage 3: Validate and submit the files

Files are validated, uploaded and submitted using the [Webin command line submission interface](cli_01.html). 
Please refer to the [Webin command line submission interface](cli_01.html) documentation for more information 
about the submission process.

## Assigned accession numbers

Once the sequences have been submitted an analysis (ERZ) accession number is immediately assigned and 
returned to the submitter by the Webin command line submission interface. 

The purpose of the ERZ accession number is for the submitter to be able to refer to their submission within the 
Webin submission service. For example, the submitter can retrieve the assigned sequence accessions 
from the [Webin XML and reports portal](prog_11.html) or from the [Webin reports service](prog_10.html) using
the ERZ accession number.

For sequences, long term stable accession numbers that can be used in publications are:

- Study accession (PRJ) assigned at time of study registration.
- Sequence accession(s) assigned once the submission has been fully processed by ENA.

Submitters can retrieve the sequence accession numbers from the [Webin XML and reports portal](prog_11.html) 
or from the [Webin reports service](prog_10.html). These accession numbers are also send to the submitters by
e-mail.