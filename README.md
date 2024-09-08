# MAT11-ERP-Code-Repository

## Dynamic Beta Estimation Using Kalman Filter and Linear Regression Models

This repository contains the code and materials for estimating dynamic beta under the Capital Asset Pricing Model (CAPM) framework using two different models: a traditional Linear Regression model (Model A) and a Kalman Filter model (Model B). The project focuses on analyzing two distinct time periods, 2015-2019 and 2020-2023, to evaluate the performance of both models under different market conditions—stable and volatile. It should also be noted that I worked on a macOS local machines and some commands specified in this readme can be macOS specific. A thorough effort has been made to ensure alternate commands are provided, but in the case a command doesn't work, the reader is encouraged to search that command in browser and get more info on it for their own specific operating system.

## Environment Setup

To achieve reproducibility, it’s important to use the exact versions of Python and the Python packages that were used during development. This guide assumes you're using Conda for environment management (a helpful guide can be found about this [here](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html).

### Step 1: Create and Activate the Conda Environment

In your terminal, run the following commands to create a virtual environment with Python 3.8 and the necessary packages:

```bash
# Create a new directory for the project
mkdir dynamic-beta-estimation

# Navigate into the directory
cd dynamic-beta-estimation

# Create a new conda environment with Python 3.11.4
conda create -n dynamic_beta_env python=3.11.4

# Activate the environment
conda activate dynamic_beta_env
```
### Step 2: Install the Required Packages
- Once the environment is activated, install the following specific package versions to ensure complete reproducibility. It should be noted that the commands should be ran individually in order to NOT have dependency issues and conflicts.

```bash
pip install yfinance==0.2.41
pip install pandas==1.5.3
pip install matplotlib==3.7.1
pip install numpy==1.24.3
pip install seaborn==0.12.2
pip install scipy==1.10.1
pip install plotly==5.9.0
pip install statsmodels==0.14.0
```
- For Git installation
    - For windows and Linux , visit [this](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) link
    - For macos, run the command
        - ```bash
          git --version
          ```
- For Jupyter Notebook Installation
    - ```bash
      # Install Jupyter Notebook and all necessary dependencies
        pip install jupyter notebook jupyterlab jupyter-server jupyter-client

      # Install ipykernel, which allows Jupyter to run Python kernels
        pip install ipykernel
      ```

### Step 3: Clone the Repository 
To get the project files, clone the repository to your local machine
```bash
git clone https://github.com/Rakshit-Yadav/MAT11-ERP-Code-Repository

# navigate into the project folder
cd MAT11-ERP-Code-Repository
```

### Step 4: Launch Jupyter Notebook
To run the project’s Jupyter notebooks, execute the following command to launch the Jupyter server:

```bash
jupyter notebook
```
This will open a browser window where you can navigate to the folder containing the notebooks.

## Project Structure
The project is structured into two main folders, each corresponding to a different time period for the analysis:

```scss
.
├── 2015-2019
│   ├── Data-Gen-EDA-Preprocess(2015-2019).ipynb
│   ├── Model-A-(2015-2019).ipynb
│   ├── KF-Model-(2015-2019).ipynb
│   └── transformed_returns_(2015-2019).csv
└── 2020-2023
    ├── Data-Gen-EDA-Preprocess(2020-2023).ipynb
    ├── Model-A-(2020-2023).ipynb
    ├── KF-Model-(2020-2023).ipynb
    └── transformed_returns_(2020-2023).csv
```

## Running The Notebooks

### Data Preprocessing

- Data-Gen-EDA-Preprocess.ipynb:
  - This notebook retrieves financial data using the yfinance package, applies preprocessing techniques (such as calculating returns, filtering outliers, etc.), and generates the CSV files required by both models.

- Running the Preprocessing:
  - Navigate to the folder (2015-2019 or 2020-2023) and open the Data-Gen-EDA-Preprocess.ipynb notebook.
  - Run all cells to generate the processed data in CSV format.

- Model A - Linear Regression
Model-A-(year_range).ipynb:
  - This notebook implements a traditional linear regression model to estimate static beta.
  - Run this notebook after generating the processed data to fit and evaluate the model on the provided dataset.

- Model B - Kalman Filter
KF-Model-(year_range).ipynb:
  - This notebook applies a Kalman Filter model to estimate time-varying beta.
  - Similar to the linear regression model, run this notebook after the preprocessing to compare model performance.

- CSV Files
  - The processed CSV files transformed_returns_(2015-2019).csv and transformed_returns_(2020-2023).csv are generated from the preprocessing notebook and are used as inputs for both models.


## Reproducibility and Notes
- The specified versions of the Python packages are critical for ensuring consistent results. Ensure you are using the exact versions mentioned above.
- The project is built using daily returns data from Yahoo Finance, making it subject to data availability. The results you reproduce may vary slightly if new data has been added to the Yahoo Finance database since this project was last run.


This project accompanies a larger research project report on the estimation of dynamic beta in financial markets using state-space models, which is submitted separately to the University of Manchester.
