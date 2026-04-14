# used-car-analysis.ipynb
For your second task involving the used car dataset, your README.md should focus on the Exploratory Data Analysis (EDA) findings and the importance of the Baseline Model.

Here is a structured template you can use for this specific repository.

Used Car Data Cleaning & Baseline Modeling
This project focuses on the initial stages of the data science lifecycle: identifying data quality issues, performing systematic cleaning, and establishing a performance baseline using Mean Absolute Error (MAE).

1. Data Quality Issues Identified
Upon initial exploration of the raw dataset using df.info() and df.describe(), the following issues were identified and addressed:

Target Nulls: Missing values in the selling_price column which would render training ineffective.

Incorrect Data Types: The mileage column contained string characters (e.g., "km", "miles"), preventing numerical analysis.

String Inconsistency: The brand column contained mixed casing and whitespace (e.g., " Toyota" vs "toyota").

Duplicate Records: Redundant rows that could bias the model's understanding of feature importance.

2. Cleaning Pipeline
The cleaning script performs the following operations:

Target Filtering: Removes any records where the price is unknown.

Regex Extraction: Uses regular expressions to strip non-numeric characters from mileage strings.

Median Imputation: Fills missing mileage values with the median to maintain the distribution while handling gaps.

Text Standardization: Converts all brand names to lowercase and removes leading/trailing spaces.

Deduplication: Ensures every record in the final dataset is unique.

3. Baseline Evaluation
Before applying advanced Machine Learning models, a Baseline Model was established by predicting the mean selling price for every car in the dataset.

Metric used: Mean Absolute Error (MAE).

Purpose: This provides a reference point. Any future predictive model (Regression, Random Forest, etc.) must achieve an MAE significantly lower than this baseline to be considered useful.

Requirements
pandas

numpy

scikit-learn

How to Use
Clone the repo.

Open used_car_cleaning.ipynb.

Run all cells to view the transition from raw messy data to the final MAE calculation.
