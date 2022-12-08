# SARS-CoV-2 build for Kenya

This repository includes an example configuration file for running a Nextstrain analysis of SARS-CoV-2 genomes from GISAID for Kenya.


## Data GISAID

Sequence data downloaded from GISAID database and processed


```bash
open ../ncov-kenya/builds.yaml
```

Edit the Auspice configuration, setting the `build_url` and `maintainers`, as needed.


## Run the analysis

Run the workflow.

``` bash
nextstrain build . -j 4 -p --configfile ../ncov-kenya/builds.yaml
```

## Inspect the analysis

View the resulting tree locally with Auspice.

```bash
nextstrain view auspice/
```

Open the local Auspice server at http://localhost:4000/.
