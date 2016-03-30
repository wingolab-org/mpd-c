MPD - Multiplex PCR Design
============================

by Thomas Wingo and David Cutler

## Description

MPD is a program designed to automate creation of multiplex primer design written in C. The `mpd_lessGreedy` and `mpd_moreGreedy` binaries differ in which primer pool they choose to start with for pool creation. Either binary can be used as stand-alone or in conjunction with the [MPD perl package](http://github.com/wingolab-org/mpd-perl).

## Installation
- Clone the repository
- Make with `make all`
- Binaries will be compiled and saved to the `build` directory

## Build Hashed Genome
- Download the genome of interest as a fasta file
- Use `bin/run_index.pl`, which creates a sh script to run `index_genome`

## Flat dbSnp
- Download and decompress the flat files for variant sites that should be avoided when designing primers. For instance, dbSNP maintains a list for most organisms and you will find the proper format in the `ASN1_flat` directory. The human data is located here: `ftp://ftp.ncbi.nih.gov/snp/organisms/human_9606_b146_GRCh38p2/ASN1_flat/`.
- Prepare a `sdx` file that contains the number of chromsome files to include as the 1st line and then a list of the names of all chromosome files. On the command line you might try: `ls -1 *.line | wc -l > db_flat.sdx; ls -1 >> db_flat.sdx`. Note that the sdx should be in the same order that the chromsomes are in for the indexed genome. See the genome's sdx file (e.g., `cat hg38.d14.sdx`) to see the order.

##  Run mpd
- The easiest way of using MPD is to use the [Perl pacakge MPD](http://github.com/wingolab-org/mpd-perl), but either `mpd_lessGreedy` and `mpd_moreGreedy` binaries may be executed from the command line interactively.
