# Can We Beat Silicon?

This project involves using machine learning to identify better semiconductor materials, specifically in comparison to silicon which is currently the standard.

## Background
### Current Industry Standard + History

Currently in industry, Silicon is used because it has a band gap of ~1.1 eV, making it ideal for controllable conductivity, as well as switching behaviour (transistors). As such

### Background Theory
- Knowledge surrounding Band Gaps, relationship between composition and properties
- DFT data and the influence of quantum mechanics to materials properties
- Machine Learning - regression models, feature engineering and model evaluation
- Data analysis and visualisation

## Motivation
Why this matters (semiconductors, tech, etc.)

## Data
Where the data comes from (Materials Project)

## Methods
### Step-by-step Aims
Firstly, a dataset of materials needs to be located, ideally including information such as chemical composition, structure and band gap (the most important). This can be sourced from places such as the **Materials Project API**, which contains DFT-computed data. My first step was to use this API to generate my own key which I used in my notebooks to access the data through a windows environment variable.

Next, predictive models need to be built and trained using the materials data. Example models include Linear Regression (baseline) and Random forest / gradient boosting.

Finally, the model can be used to identify materials with band gaps in the desired range (~1-2 eV), and compare them to the silicon industry standard.

### Implementation
To start with, a simple stack would include the following :
- NumPy, pandas and matplotlib / seaborn for numerical operations, data handling and plotting
- scikit-learn for the machine learning regression models and evaluation metrics
- pymatgen and Materials Project API to handle materials structures, extract features, and source the DFT data

All of this will be handled within a Jupyter Notebook

## Progress Logs
- Created project file, installed necessary packages (mp-api and pymatgen) which involved some fiddling around with anaconda and it's environments to ensure proper installation.



## Results
Key findings (with 1–2 images)

## Key Insights
Bullet points of what you discovered

## Limitations / Reflection
Be honest (this is impressive)

## How to Run
Instructions (pip install, etc.)
