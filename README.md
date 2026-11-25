# Semiconductor Materials Data Exploration

An independent, ongoing project using Materials Project computational data to explore semiconductor-relevant properties.

**Current stopping point:** the initial data-quality and exploratory-analysis stage is complete. The notebook runs from top to bottom, includes saved outputs and ends with a checkpoint summary. Predictive modelling is a separate future stage; no models have been trained or evaluated.

## Explore the notebook

Open [the Jupyter notebook](notebook/materials-research-project.ipynb) to follow six sections:

1. Environment and query settings.
2. Data retrieval or reload from a local cached snapshot.
3. Identifier, range, data-type and missing-value checks.
4. Descriptive statistics and a computed silicon reference.
5. Band-gap distribution and density comparison.
6. A generated checkpoint summary, interpretation limits and next steps.

The query selects computed band gaps from **0.1 to 5.0 eV** and retains 11 properties. Analysis uses Python, pandas, NumPy, Matplotlib and the `mp-api` client.

## Verified snapshot

The live query was run on **2026-11-25**. A subsequent cache-only run, with the API key removed from the test process, also completed successfully.

| Check | Result |
|---|---:|
| Material records | 72,570 |
| Analysis columns | 11 |
| Duplicate material IDs | 0 |
| Missing `is_metal` values, retained as unknown | 38 |
| Records excluded from the density plot | 0 |
| Computed-gap median within the selected sample | 1.7713 eV |

Chemical formulas such as `NaN` are preserved as text when reloading CSV data. Missing optional values are reported rather than globally dropped or imputed. The current plots describe a selected computational dataset; they do not establish model performance, device suitability or a replacement for silicon.

## Run locally

```bash
git clone https://github.com/sumi-ctrl/materials-research-project.git
cd materials-research-project
conda env create -f environment.yml
conda activate materials-research
jupyter notebook notebook/materials-research-project.ipynb
```

Set `MP_API_KEY` in your local environment before starting Jupyter for the first download. Credentials are not stored in the notebook or cache.

Run from the repository root or its `notebook/` directory. Local data, a query/provenance record and a generated summary are written to the git-ignored `data/` directory. Future runs use that cache without an API key; set `REFRESH_DATA = True` to deliberately query again. Query settings and the CSV hash are checked before a cached snapshot is used.

The cache is not distributed with the repository. Database updates may change results on a fresh download. `environment.yml` is the setup specification; `requirements.txt` is a Windows Conda export, not a pip requirements file. The existing environment was used for validation; recreating it on another machine was not tested. Import-time environment notices are retained in a collapsible notebook output.

## Next stage

Define a focused prediction task, review property provenance and missingness, choose composition or structure descriptors, and establish an appropriate validation split before training a baseline. Band gap alone is insufficient to determine a material's suitability for a semiconductor application.

The original question, “Can we beat silicon?”, remains a longer-term motivation rather than a result of this exploratory stage.

## Data source

[Materials Project](https://materialsproject.org/) and its [official API examples](https://docs.materialsproject.org/downloading-data/using-the-api/examples). These are database-derived computational values, not experimental measurements performed in this project.
