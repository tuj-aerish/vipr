# ![nf-core/vipr](docs/images/vipr_logo.png)

[![Build Status](https://travis-ci.org/nf-core/vipr.svg?branch=master)](https://travis-ci.org/nf-core/vipr)
[![Nextflow](https://img.shields.io/badge/nextflow-%E2%89%A50.27.6-brightgreen.svg)](https://www.nextflow.io/)
[![Gitter](https://img.shields.io/badge/gitter-%20join%20chat%20%E2%86%92-4fb99a.svg)](https://gitter.im/nf-core/Lobby)
[![Docker Container available](https://img.shields.io/docker/automated/nfcore/vipr.svg)](https://hub.docker.com/r/nfcore/vipr/)
![Singularity Container available](
https://img.shields.io/badge/singularity-available-7E4C74.svg)


### Introduction

**nf-core/vipr** is a bioinformatics best-practice analysis pipeline
used for viral amplicon analysis and intrahost / low-frequency variant
calling.

The pipeline uses [Nextflow](https://www.nextflow.io), a
bioinformatics workflow tool. It pre-processes raw data from FastQ
inputs, aligns the reads and performs extensive quality-control on the
results.

ViPR mainly started out as an ecosystem around LoFreq an went through
a couple of iterations. The current version had three predecessors
[ViPR 1](https://github.com/CSB5/vipr),
[ViPR 2](https://github.com/CSB5/vipr2) and [ViPR
3](https://github.com/gis-rpd/pipelines/tree/master/germs/vipr)

An incomplete list of publications using (previous versions of) ViPR:

- [Sessions et. al., PLoS Negl Trop Dis., 2015](https://www.ncbi.nlm.nih.gov/pubmed/26327586)
- [Sim et al., PLoS Negl Trop Dis., 2015](https://www.ncbi.nlm.nih.gov/pubmed/26325059)


### Pipeline Steps

| Step                                                | Main program/s                      |
|-----------------------------------------------------|-------------------------------------|
| Trimming, combining of read-pairs per sample and QC | Skewer, FastQC                      |
| Decontamination                                     | decont: BWA                         |
| Metagenomics classifcation / Sample purity          | Kraken                              |
| Assembly to contigs                                 | BBtools' Tadpole                    |
| Assembly polishing                                  | ViPR Tools: Mummer's Nucmer, LoFreq |
| Mapping to assembly                                 | BWA, LoFreq                         |
| Low frequency variant calling                       | LoFreq                              |
| Coverage and variant AF plots (two processes)       | Bedtools, ViPR Tools                |



### Documentation

Documentation about the pipeline can be found in the `docs/` directory:

1. [Installation and configuration](docs/installation.md)
2. [Running the pipeline](docs/usage.md)
3. [Output and how to interpret the results](docs/output.md)


### Credits

This pipeline was developed at the [Genome Institute of Singapore](http://a-star.edu.sg/gis)
by [Andreas Wilm](https://github.com/andreas-wilm/).

Plenty of people provided essential feedback, including:

- [October SESSIONS](https://www.duke-nus.edu.sg/content/sessions-october)
- [Paola Florez DE SESSIONS](https://www.a-star.edu.sg/gis/Our-People/Platform-Leaders)
- ZHU Yuan
- Shuzhen SIM
- CHU Wenhan Collins