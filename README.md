# RTG Tools

Copyright (c) 2014 Real Time Genomics Ltd

This software is provided under the Simplified BSD License. See
[LICENSE.txt](LICENSE.txt)

## Introduction

RTG Tools includes several useful utilities for dealing with VCF files
and sequence data, but probably the most interesting is the `vcfeval`
command which performs sophisticated comparison of VCF
files.

Conventional tools attempt comparison by directly comparing variant
positions, alleles, and genotypes, however they are inherently unable
to deal with differences in representation that commonly arise,
particularly when dealing with complex variants or when comparing
variants produced by different callers.  More details are in this
presentation on
[slideshare](http://www.slideshare.net/GenomeInABottle/140127-rtg-vcfeval-vcf-comparison-tool).
Comparison approaches based on normalization or decomposition can
alleviate these problem but often fail to deal with more complex
situations.

RTG vcfeval performs variant comparison at the haplotype level, that
is, it determines whether the genotypes asserted in the VCFs under
comparison result in the same genomic sequence when applied to the
reference genome.  This in itself is a non-trivial problem and naive
approaches face a combinatorial explosion to determine the most
accurate analysis.  To date, no other tool is capable of performing
this analysis as accurately and as fast as RTG vcfeval.  RTG developed
vcfeval for in-house use in 2010, and through our collaborations we
found this tool to be highly useful outside of RTG.  In order to
encourage wider adoption of best-practise methods for variant
comparison and benchmarking, Real Time Genomics made RTG Tools freely
available, and now this includes the source code under an OSI approved
open source licence.  RTG Tools are mature, well tested, and under
ongoing development.

RTG Tools is available pre-packaged directly from our
[website](http://realtimegenomics.com/products/rtg-tools/), or follow
the instructions below to build from this repository.

## Support

A PDF user manual is included in the installation or can be
[viewed online](installer/resources/tools/RTGOperationsManual.pdf).

You can use the commands in RTG Tools to format your own reference
datasets, or download common
[pre-formatted references](http://realtimegenomics.com/news/pre-formatted-reference-datasets/)
from our website.

An
[rtg-users](https://groups.google.com/a/realtimegenomics.com/forum/#!forum/rtg-users)
discussion group is now available for general questions, tips, and
other discussions.

To be informed of new software releases, subscribe to the low-traffic
[rtg-announce](https://groups.google.com/a/realtimegenomics.com/forum/#!forum/rtg-announce)
group.

---

## Prerequisites for building from source

* Java 1.7 or later
* apache ant 1.9 or later

## Check out source code for RTG Tools

    $ git clone https://github.com/RealTimeGenomics/rtg-tools.git
    $ cd rtg-tools

## Compile / run unit tests

    $ ant runalltests

## Build RTG Tools package

To build the RTG Tools package which can be locally installed and run:

    $ ant zip-nojre

This will create an installation zip file under `dist`.

## Installation

Uncompress the installation zip:

    $ cd /my/install/dir/
    $ unzip /path/to/rtg-tools/dist/rtg-tools-VERSION-nojre.zip

Follow the instructions contained in the `README.txt`. This build will
use the system Java by default, so ensure that it is Java 1.7 or
later.


