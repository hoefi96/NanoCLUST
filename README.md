# NanoCLUST

**De novo clustering and consensus building for ONT 16S sequencing data**.

## Introduction

The pipeline is built using [Nextflow](https://www.nextflow.io), a workflow tool to run tasks across multiple compute infrastructures in a very portable manner. It comes with docker containers making installation trivial and results highly reproducible.

## Quick Start

i. Install [`nextflow`](https://nf-co.re/usage/installation)

ii. Install [`docker`](https://docs.docker.com/engine/installation/) or [`conda`](https://conda.io/miniconda.html)

iii. Clone the NanoCLUST repository and test the pipeline on a minimal dataset with a single command

*Download a BLAST database for cluster sequence classification. For NCBI 16S rRNA database:

```bash
mkdir db db/taxdb
wget https://ftp.ncbi.nlm.nih.gov/blast/db/16S_ribosomal_RNA.tar.gz && tar -xzvf 16S_ribosomal_RNA.tar.gz -C db
wget https://ftp.ncbi.nlm.nih.gov/blast/db/taxdb.tar.gz && tar -xzvf taxdb.tar.gz -C db/taxdb
```

```bash
nextflow run main.nf -profile test,<docker/conda>
```

iv. Start running your own analysis!

Run a single sample analysis using default parameters:

```bash
nextflow run nf-core/nanoclust -profile conda --reads 'sample.fastq' --db "path/to/nanoclust/db/16S_ribosomal_RNA" --tax "path/to/nanoclust/db/taxdb/"
```

See usage and output sections in the documentation (/docs) for all of the available options when running the pipeline.


## Credits

Rodríguez-Pérez H, Ciuffreda L, Flores C (2020). NanoCLUST: a species-level analysis of 16S rRNA nanopore sequencing data. Submitted.

This work was supported by Instituto de Salud Carlos III [PI14/00844, PI17/00610, and FI18/00230] and co-financed by the European Regional Development Funds, “A way of making Europe” from the European Union; Ministerio de Ciencia e Innovación [RTC-2017-6471-1, AEI/FEDER, UE]; Cabildo Insular de Tenerife [CGIEU0000219140]; Fundación Canaria Instituto de Investigación Sanitaria de Canarias [PIFUN48/18]; and by the agreement with Instituto Tecnológico y de Energías Renovables (ITER) to strengthen scientific and technological education, training, research, development and innovation in Genomics, Personalized Medicine and Biotechnology [OA17/008]. 

## Contributions and Support

If you would like to contribute to this pipeline, please see the contributing guidelines

For further information or help, don't hesitate to get in touch on [Slack](https://nfcore.slack.com/channels/nf-core/nanoclust) (you can join with [this invite](https://nf-co.re/join/slack)).
