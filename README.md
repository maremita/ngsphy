
# NGSphy

[![Build Status](https://travis-ci.org/merlyescalona/ngsphy.svg?branch=master)](https://travis-ci.org/merlyescalona/ngsphy) [![PyPI version](https://badge.fury.io/py/ngsphy.svg)](https://badge.fury.io/py/ngsphy) [![Join the chat at https://gitter.im/ngsphy/Lobby](https://badges.gitter.im/ngsphy/Lobby.svg)](https://gitter.im/ngsphy/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

© 2017 Merly Escalona (<merlyescalona@uvigo.es>), Sara Rocha, David Posada

University of Vigo, Spain ([http://darwin.uvigo.es](http://darwin.uvigo.es))

## About NGSphy
NGSphy is a Python open-source tool for the genome-wide simulation of NGS data (read counts or Illumina reads) obtained from thousands of gene families evolving under a common species tree, with multiple haploid and/or diploid individuals per species, where sequencing coverage (depth) heterogeneity can vary among species, individuals and loci, including off-target and untargeted loci.

## Documentation

The documentation is available [here](https://github.com/merlyescalona/ngsphy/wiki)

## Citation

- If you use NGSphy, please cite:
    - Escalona, M, Rocha S and Posada D. *NGSphy: phylogenomic simulation of NGS data*. bioRxiv 197715; doi: https://doi.org/10.1101/197715
    - Sukumaran, J and Holder MT. (2010). *DendroPy: A Python library for phylogenetic computing*. Bioinformatics 26: 1569-1571.

- if running ART cite also:
    - Huang W, Li L, Myers JR and Marth, GT. (2012) *ART: a next-generation sequencing read simulator*. Bioinformatics  28 (4): 593-594

- if using SimPhy cite also:
    - Mallo D, De Oliveira Martins L and Posada D. (2016). *SimPhy : Phylogenomic Simulation of Gene, Locus, and Species Trees*. Systematic Biology 65(2): 334-344.

- if using single gene tree inputs, cite also:
    - Fletcher, W and Yang Z. (2009) *INDELible: A flexible simulator of biological sequence evolution*. Molecular Biology and Evolution. 26 (8): 1879–88.

# Input/output files

## Input

[Single gene-tree scenario]
- NGSPhy settings file
- INDELible control file
- [Newick file](http://evolution.genetics.washington.edu/phylip/newicktree.html) with single gene tree
- ancestral sequence file ([FASTA](https://en.wikipedia.org/wiki/FASTA_format)) (optional)
- reference allele file (optional)

[Species-tree scenario]
- NGSPhy settings file
- SimPhy output
- reference allele file (optional)

## Output files
- NGS reads:
    - [FASTQ](https://en.wikipedia.org/wiki/FASTQ_format)
    - [ALN](http://meme-suite.org/doc/clustalw-format.html)
    - [BAM](https://samtools.github.io/hts-specs/)
- read counts:
    - [VCF](https://samtools.github.io/hts-specs/)
- sequence alignments:
    - [FASTA](https://en.wikipedia.org/wiki/FASTA_format)
- coverage variation
    - [CSV](https://en.wikipedia.org/wiki/Comma-separated_values)
- log files
- bash scripts

# Usage

NGSphy does not have a Graphical User Interface (GUI) and works on the Linux/Mac command line in a non-interactive fashion.

```
usage: ngsphy  [-s <settings_file_path>]
               [-l <log_level>] [-v] [-h]
```

- Optional arguments:
    - `-s <settings_file_path>, --settings <settings_file_path>`:
        - Path to the settings file. This is optional, by default NGSphy loos for a `settings.txt` file in the current working directory. You can also specify a particular settings file with:
        ```
        ngsphy -s settings.txt
        ```
    - `-l <log_level>, --log <log_level>`: Specified hierarchical log levels that will be shown through the standard output. A detailed log will be stored in a separate file. Possible values:
        - `DEBUG`: shows very detailed information of the program's process.
        - `INFO` (default): shows only information about the state of the program.
        - `WARNING`: shows only system warnings.
        - `ERROR`: shows only execution errors.

- Information arguments:
    - `-v, --version`: Show program's version number and exit.
    - `-h, --help`: Show help message and exit.


## Quick start guide:

NGSphy simulates

- To find possible NGSphy settings go [here](https://github.com/merlyescalona/ngsphy/tree/master/data/settings)
- To find possible INDELible control files go [here](https://github.com/merlyescalona/ngsphy/tree/master/data/indelible)
- To find possible reference allele files go [here](https://github.com/merlyescalona/ngsphy/tree/master/data/reference_alleles)

- Tutorials for each input mode can be found [here](https://github.com/merlyescalona/ngsphy/wiki/Tutorials-setting-examples)

[Single gene-tree scenario]

NGSPhy settings file
INDELible control file
Newick file with single gene tree
ancestral sequence file (FASTA) (optional)
reference allele file (optional)

[Species-tree scenario]

NGSPhy settings file
SimPhy output
reference allele file (optional)
