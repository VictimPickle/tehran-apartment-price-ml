# Tehran Apartment Price Prediction - Machine Learning

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Real Estate](https://img.shields.io/badge/Domain-Real%20Estate-orange)]()

**Real Estate Price Prediction** - Predicting apartment prices in Tehran using data cleaning, feature engineering, and regression models.

## 📊 Overview

This project analyzes Tehran's real estate market to build predictive models for apartment pricing. Uses comprehensive feature engineering on real-world listing data including area, rooms, amenities, and neighborhood information.

**Key Features:**
- ✅ Data cleaning & preprocessing pipeline
- ✅ Comprehensive feature engineering
- ✅ Linear & polynomial regression models
- ✅ Model comparison & evaluation
- ✅ Real Tehran apartment market data

## 🛠️ Technologies

```
Python | Pandas | NumPy | Scikit-learn | Matplotlib
```

## 🏠 Dataset Features

- **Property Data:** Area (m²), rooms, parking, elevator
- **Location:** Neighborhood, district, zone
- **Amenities:** Garden, balcony, furnished status
- **Market Data:** Price (target variable)

## 🔍 Models

**Linear Regression:** Baseline model  
**Polynomial Regression:** Captures non-linear relationships  
**Ridge/Lasso:** Regularized models for robustness  

## 🚀 Quick Start

```bash
git clone https://github.com/VictimPickle/tehran-apartment-price-ml.git
cd tehran-apartment-price-ml
pip install pandas numpy scikit-learn matplotlib jupyter
jupyter notebook
```

## 📈 Results

**Best Model:** Polynomial Regression (degree 2)  
**R² Score:** 0.87  
**Mean Absolute Error:** ~50M Tomans  

**Key Insights:**
- Area is the strongest price predictor
- Neighborhood significantly impacts price
- Amenities add 5-15% to base price

---

**Created by:** Mobin Ghorbani | December 2025
