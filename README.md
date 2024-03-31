# House Price Dataset EDA

## Project Overview
This exploratory data analysis (EDA) focuses on the **House Price** dataset, which includes a wide range of features potentially useful for predicting house prices. The goal is to thoroughly understand the data, clean it, and transform it into a machine learning-ready format.

## Data Source
The dataset used in this analysis can be found at [github.com/ArinB/MSBA-CA-Data/CA01](https://github.com/ArinB/MSBA-CA-Data/tree/main/CA01). It consists of various features related to house characteristics and pricing in the training set. For this project, we solely work with the training data to prepare it for machine learning models.

## Data Preparation
The data preparation process is detailed in the `eda.ipynb` notebook and includes several crucial steps:

### Data Cleaning and Understanding
- **Categorization**: Continuous and categorical features are identified, including special handling for `MSSubClass` as a categorical feature despite its numerical representation.
- **Data Quality Reports**: Generation of data quality report tables for continuous and categorical features to highlight missing values, cardinality, and descriptive statistics.
- **Visualizations**: Histogram and bar plots for key continuous and categorical features are generated to understand their distribution in the training data. 

### Feature Engineering
- **Handling Missing Values**: Detailed analysis and imputation strategies for missing values in both continuous and categorical features. Continuous features with missing values, such as `LotFrontage` and `GarageYrBlt`, are imputed with median values or specific placeholders, while categorical features with high percentages of missing values (`Alley`, `MasVnrType`, `PoolQC`, `Fence`, and `MiscFeature`) are dropped from the dataset.
- **Handling Outliers**: Outliers in continuous features are identified using IQR (Interquartile Range) and addressed through transformations.
- **Encoding**: Ordinal features are encoded based on intrinsic order, and nominal features undergo one-hot encoding to convert them into a machine learning-compatible format.
- **Normalization and Scaling**: Continuous features are normalized to ensure model sensitivity is accounted for.
- **Feature Selection**: Based on collinearity analysis, including the calculation of Variance Inflation Factors (VIF) and correlation matrices, features with high multicollinearity are identified and dropped to ensure the dataset's readiness for modeling.

### Saving Processed Data
The data processing steps generate three files to capture the stages of data transformation:
- `house-price-train-cleaned.csv`: Data after cleaning but before encoding.
- `house-price-train-cleaned-encoded.csv`: Data after cleaning and encoding categorical features.
- `house-price-train-cleaned-encoded-feature-selected.csv`: Data post-cleaning, encoding, and feature selection to address collinearity issues.

## Repository Structure
- `eda.ipynb`: Python notebook detailing the data preparation process.
- `house-price-train.csv`: Training data of the house price dataset.
- `data_description.txt`: Detailed description of dataset features.

## Installation

Before running the scripts, ensure you have Python installed on your system. You'll need the following dependencies:

- pandas
- numpy
- scikit-learn
- scipy
- statmodels
- matplotlib
- seaborn

You can install all required packages using the following command:

```bash
pip install pandas numpy scikit-learn scipy statmodels matplotlib seaborn
```

## Usage
To replicate the analysis, run the cells in `eda.ipynb` sequentially, which will process the data through the stages described above and generate the processed data files.

<!-- ## Conclusion
This EDA project demonstrates a comprehensive approach to preparing a complex dataset for exploratory analysis and further modeling. Through meticulous data cleaning, feature engineering, and preparation, we ensure that the dataset is primed for generating actionable insights into house price prediction. -->