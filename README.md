# Example SARS-CoV-2 build for countries in Africa

This repository includes an example configuration file for running a Nextstrain analysis of SARS-CoV-2 genomes from GISAID for a specific country (South Africa).
To make your own country-level analysis, edit this configuration file to change the country from "South Africa" to your country of choice.

## Setup your environment

[Setup the Nextstrain software environment and download the ncov workflow](https://nextstrain.github.io/ncov/setup.html).

## Curate data from GISAID

[Select data from GISAID for your country and for phylogenetic context](https://nextstrain.github.io/ncov/data-prep.html).

## Run the analysis

Download this repository into the parent directory of the `ncov` workflow.

```bash
git clone https://github.com/blab/ncov-africa.git
```

Change directories to the `ncov` workflow.

``` bash
cd ncov/
```

Edit the workflow configuration for your country, as needed.
For example, change instances of "south-africa" and "South Africa" to your country of interest.

```bash
open ../ncov-africa/builds.yaml
```

Run the workflow.

``` bash
nextstrain build . -j 4 -p --configfile ../ncov-africa/builds.yaml
```
