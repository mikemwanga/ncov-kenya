# Example SARS-CoV-2 build for countries in Africa

This repository includes an example configuration file for running a Nextstrain analysis of SARS-CoV-2 genomes from GISAID for a specific country (South Africa).
To make your own country-level analysis, edit this configuration file to change the country from "South Africa" to your country of choice.

[View the tree from this analysis through Nextstrain's community interface](https://nextstrain.org/community/blab/ncov-africa@main/south-africa).

## Setup your environment

[Setup the Nextstrain software environment and download the ncov workflow](https://nextstrain.github.io/ncov/setup.html).
For example, to download the workflow you can run the following command.

```bash
git clone https://github.com/nextstrain/ncov.git
```

## Curate data from GISAID

[Select data from GISAID for your country and for phylogenetic context](https://nextstrain.github.io/ncov/data-prep.html).
Download these data files into your `ncov/data/` directory.
For this analysis, we will use recent data from South Africa and the recent "nextregions" download for Africa.

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

Dry-run the workflow (print commands without running anything).

``` bash
nextstrain build . -j 4 -n -p --configfile ../ncov-africa/builds.yaml
```

Create a graph of the workflow.

``` bash
nextstrain build . --configfile ../ncov-africa/builds.yaml --dag | dot -Tpdf > dag.pdf
```

View a graph of the workflow.

```bash
open dag.pdf
```

Run the workflow.

``` bash
nextstrain build . -j 4 -p --configfile ../ncov-africa/builds.yaml
```

## Inspect the analysis

View the resulting tree locally with Auspice.

```bash
nextstrain view auspice/
```

Open the local Auspice server at http://localhost:4000/.
