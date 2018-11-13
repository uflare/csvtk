# CSVTK 
==========
> a cross-platform, efficient and practical CSV/TSV toolkit, it is forked from [this](https://github.com/shenwei356/csvtk) repo, but we added more subcommands like `js` based filtering and enhanced some other commands, also we'are planing to add more commands to it, you can find the origional documentation [here](http://bioinf.shenwei.me/csvtk/) plus this README that documents the added commands.

## Introduction

Similar to FASTA/Q format in field of Bioinformatics,
CSV/TSV formats are basic and ubiquitous file formats in both Bioinformatics and data sicence.

People usually use spreadsheet softwares like MS Excel to do process table data.
However it's all by clicking and typing, which is **not
automatically and time-consuming to repeat**, especially when we want to
apply similar operations with different datasets or purposes.

***You can also accomplish some CSV/TSV manipulations using shell commands,
but more codes are needed to handle the header line. Shell commands do not
support selecting columns with column names either.***

`csvtk` is **convenient for rapid data investigation
and also easy to be integrated into analysis pipelines**.
It could save you much time of writing Python/R scripts.

## Table of Contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Features](#features)
- [Subcommands](#subcommands)
- [Installation](#installation)
- [Bash-completion](#bash-completion)
- [Compared to `csvkit`](#compared-to-csvkit)
- [Examples](#examples)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact)
- [License](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Features

- **Light weight and out-of-the-box, no dependencies, no compilation, no configuration**
- **Fast**,  **multiple-CPUs supported**
- **Practical functions supported by N subcommands**
- **Support STDIN and gziped input/output file, easy being used in pipe**
- Most of the subcommands support ***unselecting fields*** and ***fuzzy fields***,
  e.g. `-f "-id,-name"` for all fields except "id" and "name",
  `-F -f "a.*"` for all fields with prefix "a.".
- **Support some common plots** (see [usage](http://bioinf.shenwei.me/csvtk/usage/#plot))
- <del>Seamlessly support for data with meta line (e.g., `sep=,`) of separator declaration used by MS Excel</del>

## Subcommands

+30 subcommands in total.

**Information**

-  `headers` print headers
-  `stats` summary of CSV file
-  `stats2` summary of selected digital fields

**Format conversion**

-  `pretty` convert CSV to readable aligned table
-  `csv2tab` convert CSV to tabular format
-  `tab2csv` convert tabular format to CSV
-  `space2tab` convert space delimited format to CSV
-  `transpose` transpose CSV data
-  `csv2md` convert CSV to markdown format
-  `xlsx2csv` convert XLSX to CSV format

**Set operations**

-  `head` print first N records
-  `concat` concatenate CSV/TSV files by rows
-  `sample` sampling by proportion
-  `cut` select parts of fields
-  `grep` grep data by selected fields with patterns/regular expressions
-  `uniq` unique data without sorting
-  `freq` frequencies of selected fields
-  `inter` intersection of multiple files
-  `filter` filter rows by values of selected fields with arithmetic expression
-  `filter2` filter rows by awk-like arithmetic/string expressions
-  `join` join multiple CSV files by selected fields
-  `split` split CSV/TSV into multiple files according to column values
-  `splitxlsx` split XLSX sheet into multiple sheets according to column values
-  `collapse` collapse one field with selected fields as keys

**Edit**

-  `rename` rename column names
-  `rename2` rename column names by regular expression
-  `replace` replace data of selected fields by regular expression
-  `replace2` replace data of selected fields using javascript function.
-  `mutate` create new columns from selected fields by regular expression
-  `mutate2` create new column from selected fields by awk-like arithmetic/string expressions
-  `gather` gather columns into key-value pairs

**Ordering**

-  `sort` sort by selected fields

**Ploting**

- `plot` see [usage](http://bioinf.shenwei.me/csvtk/usage/#plot)
    - `plot hist` histogram
    - `plot box` boxplot
    - `plot line` line plot and scatter plot

**Misc**

- `version`   print version information and check for update
- `genautocomplete` generate shell autocompletion script


## Installation
