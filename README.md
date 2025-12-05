# Tehran House Price Prediction

## Project Overview
This project analyzes a dataset of about 4,000 real estate listings in Tehran to predict housing prices. The goal is to build regression models that estimate property value based on features such as area, number of rooms, location, and amenities, and to compare a multiple linear regression model with a polynomial regression model.

## Dataset
Columns in `housePrice.csv`:
- Area: Property size in square meters.
- Room: Number of bedrooms.
- Parking: Has parking (0/1).
- Warehouse: Has storage (0/1).
- Elevator: Has elevator (0/1).
- Address: Neighborhood/location in Tehran.
- Price: Listing price in Toman.
- Price(USD): Listing price in USD (not used as a feature).

## Data Cleaning
Main cleaning steps:
- Converted `Area` from string (with commas and spaces) to numeric.
- Removed unrealistic Area values (e.g., greater than 500 m²).
- Removed price outliers using the IQR (interquartile range) method.
- Dropped rows with missing `Address` values.
- Converted boolean columns (Parking, Warehouse, Elevator) to 0/1 integers.

## Feature Engineering
- Dropped the original text `Address` and `Price(USD)` from the feature set.
- Encoded `Address` as an ordered numeric feature based on its average price (more expensive neighborhoods receive higher codes).
- Final feature set:
  - Area
  - Room
  - Parking
  - Warehouse
  - Elevator
  - Address_Encoded

## Modeling
Two main models were trained and evaluated:

1. Multiple Linear Regression  
   - Trained on the 6 engineered features.  
   - Used as a baseline model.

2. Polynomial Regression (degree = 2)  
   - Generated polynomial and interaction features from the same 6 inputs.  
   - Trained a linear model on these expanded features.

The data was split into training and test sets (approximately 80% train, 20% test) using a random mask.

## Results

| Model                         | R² on Test Set |
|------------------------------|----------------|
| Multiple Linear Regression    | 0.73           |
| Polynomial Regression (deg 2) | 0.86           |

The polynomial model provides a substantial improvement in performance, capturing non‑linear relationships between features and price.

## Feature Importance (Polynomial Model)
Using permutation importance on the polynomial model, the most influential terms were:

- Area × Address_Encoded (interaction term)
- Address_Encoded
- Area²
- Interactions involving Area with other features (e.g., Area × Room, Area × Elevator)

This indicates that:
- Location (Address) strongly affects the base price level.
- The impact of Area depends on the neighborhood (location acts as a multiplier).
- Price growth with respect to Area is non‑linear for larger apartments.

## How to Run

1. Clone the repository:
   - `git clone https://github.com/your-username/tehran-house-price-prediction.git`

2. Install dependencies:
   - `pip install pandas numpy matplotlib scikit-learn`

3. Open the notebook:
   - `jupyter notebook House_Price_Prediction.ipynb`

## Conclusion
The project shows that both apartment size and location are critical for predicting housing prices in Tehran, but their interaction is even more important. A polynomial regression model of degree 2 achieves around 0.86 R² on the test set, significantly outperforming the baseline linear model and providing a useful tool for approximate price estimation.
