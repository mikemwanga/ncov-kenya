# Example SARS-CoV-2 build for countries in Africa

This repository includes an example configuration file for running a Nextstrain analysis of SARS-CoV-2 genomes from GISAID for a specific country (South Africa).

## Fork this repository

Select the "Fork" button in the top right of this repository's GitHub page.
This will make a copy of the repository in your personal or organizational GitHub account that you can edit.
Working from this forked copy, follow the instructions below to make your own country-focused Nextstrain analysis of SARS-CoV-2.

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

## Configure the analysis

Download this repository into the parent directory of the `ncov` workflow.
If you've forked this repository, replace `blab` with your username or organization.

```bash
git clone https://github.com/blab/ncov-africa.git
```

Change directories to the `ncov` workflow.

``` bash
cd ncov/
```

Edit the workflow configuration for your country, as needed.
For example, change instances of "south-africa" and "South Africa" to your country of interest.
Update the list of `inputs` to match the data you curated from GISAID.

```bash
open ../ncov-africa/builds.yaml
```

Edit the Auspice configuration, setting the `build_url` and `maintainers`, as needed.

```bash
open ../ncov-africa/auspice_config.json
```

## Review the analysis

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

## Run the analysis

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

## Save your analysis

Copy the Auspice tree files from the workflow directory into your GitHub repository.

```bash
cp auspice/* ../ncov-africa/auspice/
```

Change directories to your GitHub repository.

```bash
cd ../ncov-africa
```

Add the new Auspice JSONs to the repository and commit them.

```bash
git add auspice/*
git commit -m "Add Auspice JSONs for my country's build"
```

Push your changes to GitHub to make them public.

```bash
git push origin main
```

## View your analysis through Nextstrain

View the tree from this analysis through [Nextstrain's community interface](https://docs.nextstrain.org/en/latest/guides/share/community-builds.html).
You can view trees hosted on GitHub with a URL like `https://nextstrain.org/community/blab/ncov-africa@main/south-africa` where `blab` is your GitHub username or organization, `ncov-africa` is the repository, `main` is the branch, and `south-africa` corresponds to a file in the repository named `ncov-africa_south-africa.json`.

## Learn more

[See the Nextstrain SARS-CoV-2 tutorial](http://nextstrain.github.io/ncov) for more details about the workflow and [see the Nextstrain documentation](http://docs.nextstrain.org/) for more about the tools behind the workflow.

If you have questions, [let us know on the Nextstrain discussion site](https://discussion.nextstrain.org/) and we'll do our best to help.
