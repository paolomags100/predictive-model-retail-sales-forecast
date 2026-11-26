# 🧪 Building a Reliable Retail Sales Forecasting Model 
*insert model image here*

## 🧠 About this Project 
This project is all about demonstrating my end-to-end data science process, with a key focus on building a machine learning model that can reliably forecast future retail sales.
  
This document will take you through my **entire journey of decision making process in building the final model** 

Think of this as a walkthrough of not just *what* I built, but also *why* I made certain decisions along the way.

## 🎯 Objectives of this the Project
Retail businesses often dealing with challenges when it comes to operationally preparing and predicting consumer demand for seasonal sales throughout the entire year -- affecting their inventory planning, staffing allocation and just the overall mental stress of uncertainty. 

Using a company's historical sales data -- a machine learning model can be built that can help predict their future sales in anticapation of these demands.

This project aims to:
1. **Predict future sales:** Build a machine learning model that can forecast a retailer's total weekly sales up to 12 weeks (roughly 3 months) ahead.
   
2. **Explore the data:** Dig into the numbers, uncover interesting sales patterns, and understand what factors might be driving weekly sales.

3. **Find the champion model:** Experiment with different algorithms, compare their predictive performance, and identify which model does the best job of forecasting future sales.

## 2. Datasets Used
Source: https://www.kaggle.com/datasets/noopurbhatt/retail-store-sales-forecasting-dataset

3 datasets
- sales.csv
- stores.csv
- features.csv

Dataset Coverage: Jan 2022 - Dec 2024

## 3. Methodology 

Before anything, how do I determine if my model's predictive power is even reliable for of this project? 
### 💯 Success Metrics

I wanted to establish what success would look like before getting carried away with model building and chasing better scores. So, I set a few performance requirements that the model would need to meet on unseen data (a.k.a. the test set):

(a) **Overall Forecasting Error:** WAPE below 5%, meaning the model's overall prediction errors are relatively small compared to actual sales.

(b) **Prediction Consistency:** At least 80% of weekly predictions should fall within ±5% of actual sales. *No point in having a model that's great at predicting some weeks but misses the mark on most others!*

(c) **Explained Variation:** An R² of at least 0.95, meaning the model can explain 95% of the variation in weekly sales.

The idea is not just to produce good-looking metrics, but actually provides reliable output that the business can use to plan resources better

### 🧭Approach

As for my approach, rather than going directly into data modelling and start throwing algorithms! Instead I broke down my project into  structured stages, with each stage building upon the next. Each stage has its own specific purpose in contributing to the model's reliability and predictive power... and ofcourse to well-document this journey!

Furthermore, I spent most of my time with the mindset of finding strong candidates for predictive signals... This meant rounds of **data discovery -> experimentation -> feature rationalization** and back to discovery to repeat the cycle. Because more features don't necessarily mean a better model. It's about finding the right ones!

## 4. Data Preparation, Cleaning & Transformation

Before modelling I want to do two things -- importing the right python libraries for awesome transformation....

**Importing the packages**
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import sklearn as skl
from xgboost import XGBRegressor
from scipy.stats import pearsonr, linregress
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.impute import SimpleImputer
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score
from IPython.display import display
```

And second I wanted to get a good understanding of what I was working with. This meant looking at the dataset's structure, identifying data types, understanding the granluarity and just simply getting a 'feel' of the overall quality. 

No complicated coding needed!

**Loading the 3 Datasets**
```python
path_dir = Path("data/raw")

stores = pd.read_csv(path_dir / "stores.csv")
sales = pd.read_csv(path_dir / "sales.csv")
features = pd.read_csv(path_dir / "features.csv")
```

**Size, Data Types, Granularity**
```python
# Sales - granularity -> unique store id by department per weekly date
#156K rows | 5 columns | PK: store_id
sales.info()
display(sales.head(5))
print("\n")

# Features - granularity -> unique store id by weekly date
#7.8k rows | 14 columns | PK: store_id
features.info() 
display(features.head(5))
print("\n")

# Stores granularity -> store ids
#50 rows | 4 columns | PK: store_id
stores.info() 
display(stores.head(5)) 
```

**Merging the Data on its 'primary key'**
```python
retail_sales = sales.merge(
    stores,
    on="store_id",
    how="left"
).merge(
    features,
    on=["store_id", "date"],
    how="left"
)

retail_sales = pd.DataFrame(retail_sales)
retail_sales.info()
```

-Merging datasets on appropriate keys

-Discovering and handling datatypes, missing values, duplicate records & unusual outliers


## 5. Data Discovery / EDA
-Only including Relevant finds
-Understanding the Variables

## 6. Feature Engineering
-These are the features I used for the ML Model

## 7. Model Train-Test Split Strategy
- Leakage prevetion
- 80/20 split and strategy

## 8. Model Experimentation & Results
- Model A: Linear Regression
- Model B: XGBoost
- Model Comparison

## 9. Champion Model: Feature Importance
- Interpretation

## 10. Champion Model: Residual Analysis
- Reveal struggles in model

## 11. Business Interpretation and Insights
- These are the patterns i discovered in the data
- Why these features were important
- 
