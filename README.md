# Semiconductor Materials Data Exploration

An independent, ongoing project exploring Materials Project data as a foundation for future predictive modelling of semiconductor-relevant properties.

**Current stage:** data retrieval, inspection and visualisation. No predictive models have been trained or evaluated yet.

## What is implemented

The [Jupyter notebook](notebook/materials-research-project.ipynb) currently:

- Checks API access using the silicon record `mp-149`.
- Retrieves materials with a computed band gap between 0.1 and 5.0 eV.
- Builds a pandas DataFrame containing material identifiers, composition-related descriptors, band gaps, density, stability and energy information.
- Inspects data types, summary statistics and missing values.
- Plots the band-gap distribution and band gap against density.

The saved notebook output contains **72,570 retrieved records** and an **11-column DataFrame**. These figures describe that saved run; a new API query may return a different dataset as the database changes.

## Data and tools

Data come from the [Materials Project](https://materialsproject.org/) through the `mp-api` Python client.

The implemented analysis uses Python, pandas, Matplotlib and Jupyter. The environment also includes NumPy, SciPy, pymatgen and scikit-learn for subsequent work; their installation does not mean that every package or modelling method has already been used.

## Explore or run the notebook

You can view the saved code, tables and plots directly on GitHub without running the API queries.

To run locally with Conda:

```bash
git clone https://github.com/sumi-ctrl/materials-research-project.git
cd materials-research-project
conda env create -f environment.yml
conda activate materials-research
jupyter notebook notebook/materials-research-project.ipynb
```

Set your Materials Project API key in the local `MP_API_KEY` environment variable before starting Jupyter. The notebook uses `MPRester()` to read the configured key. Keep credentials outside the notebook and repository.

Run the analysis cells in order so that the retrieved records and DataFrame exist before inspection and plotting. The saved execution counts are not sequential, so a clean, end-to-end rerun remains a reproducibility task.

Use `environment.yml` for environment setup. The existing `requirements.txt` is a Windows Conda environment export, rather than a pip requirements file.

## Interpretation and limitations

- These are database-derived computational values, not experimental measurements made in this project.
- The query selects a band-gap range, so the plots do not represent the complete Materials Project database.
- Exploratory plots describe this selected dataset; they do not establish predictive performance or identify a superior replacement for silicon.
- Band gap alone is insufficient to assess suitability for a semiconductor application.
- Data cleaning, feature selection and model evaluation remain future work.

## Planned next steps

1. Review missing values, data provenance and the treatment of theoretical versus experimentally reported structures.
2. Define a specific prediction task and suitable material descriptors.
3. Establish a baseline model, then compare appropriate alternatives using a clear train/test separation.
4. Evaluate errors and limitations before interpreting candidate materials.

The original question, “Can we beat silicon?”, remains a longer-term motivation rather than a result of the current analysis.
