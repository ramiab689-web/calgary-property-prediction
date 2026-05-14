# Predicting Residential Property Values in Calgary

Predicting residential property assessed values in Calgary using 490,000+ records from the City of Calgary Open Data Portal. Compares OLS regression and Random Forest models.

## Results

| Model | R² | RMSE |
|-------|-----|------|
| OLS Regression | 0.61 | $176,228 |
| Random Forest | 0.86 | $106,845 |

Random Forest significantly outperforms OLS, suggesting non-linear relationships between property features and assessed values. Lot size, which is nearly useless in OLS, becomes the strongest predictor in Random Forest (40.5% feature importance).

## Data

**Source:** [City of Calgary Open Data Portal — Current Year Property Assessments (Parcel)](https://data.calgary.ca/Government/Current-Year-Property-Assessments-Parcel-/4bsw-nn7w)

The dataset contains assessed values for all properties in Calgary from the 2026 assessment roll. After filtering to residential properties and cleaning, the final dataset has 489,778 observations.

**Features used:**
- Lot size (sq ft)
- Property age
- Dwelling type (Detached, Semi-Detached, Townhouse, Low-Rise Condo, High-Rise Condo)
- Land use designation
- Community median assessed value
- Community percentage of detached homes

## How to Run

1. Download the dataset from the [City of Calgary Open Data Portal](https://data.calgary.ca/Government/Current-Year-Property-Assessments-Parcel-/4bsw-nn7w) and place it in a `data/` folder as `Current_Year_Property_Assessments.csv`
2. Install dependencies:
   ```
   pip install pandas scikit-learn matplotlib seaborn
   ```
3. Open `calgary_property_prediction.ipynb` in Jupyter Notebook and run all cells

## Key Findings

- Random Forest captures non-linear relationships that OLS misses, particularly with lot size
- Community median value is the second strongest predictor, reflecting the importance of location
- Results are stable across 80/20 and 70/30 train-test splits
- Missing interior characteristics (square footage, bedrooms) are a key limitation

## Tools

Python, pandas, NumPy, scikit-learn, matplotlib, seaborn
