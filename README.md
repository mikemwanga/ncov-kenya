# Example SARS-CoV-2 build for South Africa

This repository includes an example configuration file for running a Nextstrain analysis of SARS-CoV-2 genomes from GISAID for a specific country (South Africa).
To make your own country-level analysis, edit this configuration file to change the country from "South Africa" to your country of choice.

## Run the analysis

[Setup the Nextstrain software environment and download the ncov workflow](https://nextstrain.github.io/ncov/setup.html).
Download this repository into the parent directory of the `ncov` workflow.

```bash
git clone https://github.com/blab/ncov-south-africa.git
```

Change directories to the `ncov` workflow.

``` bash
cd ncov/
```

Run the workflow.

``` bash
nextstrain build . -j 4 -p --configfile ../ncov-south-africa/builds.yaml
```
