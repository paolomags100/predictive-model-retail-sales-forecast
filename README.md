# 🧪 Building a Reliable Retail Sales Forecasting Model 
*insert model image here*

## 🧠 About this Project 
This project is all about demonstrating my end-to-end data science process, with a key focus on building a machine learning model that can reliably forecast future retail sales.
  
This .readme document will take you through my **journey of decision making in building out the final model** 

Think of this as a walkthrough of not just *what* I built, but also *why* I made certain decisions along the way.

## 🎯 Objectives of this the Project
Retail businesses often dealing with challenges when it comes to operationally preparing and predicting consumer demand for seasonal sales throughout the entire year -- affecting their inventory planning, staffing allocation and just the overall mental stress of uncertainty. 

Using a company's historical sales data -- a machine learning model can be built that can help predict their future sales in anticapation of these demands.

This project aims to:
1. **Predict future sales:** Build a machine learning model that can forecast a retailer's total weekly sales up to 12 weeks (roughly 3 months) ahead.
   
2. **Uncover the key patterns:** Dig into the numbers, uncover interesting sales patterns, and understand what factors might be driving weekly sales.

3. **Find the champion model:** Experiment with different algorithms, compare their predictive performance, and identify which model does the best job of forecasting future sales.

## 2. Retail Dataset 
Source: https://www.kaggle.com/datasets/noopurbhatt/retail-store-sales-forecasting-dataset

3 datasets
- sales.csv
- stores.csv
- features.csv

Data period: Jan 2022 - Dec 2024

## 3. Methodology 

Before anything, how do I determine if my model's predictive power is even reliable for of this project? 
### 💯 The Success Metrics

I wanted to establish what success would look like before getting carried away with model building and chasing better scores. So, I set a few **minimum** performance requirements that the model would need to meet on unseen data (a.k.a. the test set):

(a) **Overall Forecasting Error:** WAPE below 5%, meaning the model's overall prediction errors are relatively small compared to actual sales.

(b) **Prediction Consistency:** At least 80% of weekly predictions should fall within ±5% of actual sales. *No point in having a model that's great at predicting some weeks but misses the mark on most others!*

(c) **Explained Variation:** An R² of at least 0.85, meaning the model can explain 85% of the variation in weekly sales.

The idea is not just to produce good-looking metrics, but actually provides reliable output that the business can use to plan resources better

### 🧭 The Approach

As for my approach, rather than going directly into data modelling and start jamming in features and algorithms! Instead I broke down my project into  structured stages (as seen on my jupyter notebook), with each stage building upon the next. Each stage had its own specific purpose in contributing to the model's quality, reliability and predictive power... and ofcourse a well-documented journey makes things easier to backtrack!

Most of my time spent being operating in the mindset of curiosity with these 2 simple questions *"Are there existing weekly sales patterns in the data that best explain its variation through time? And how can I translate these predictive signals into features the model will understand?"*... This meant rounds of **data discovery -> experimentation -> feature rationalization** and back to discovery to repeat the cycle. Because adding more random features don't necessarily mean a better model. It's about finding the right ones!


## 5. Key Findings for Predictive Signals (EDA)

### How is weekly sales data shaped?
Across volume (distribution)

Across volume x time (weekly trend)

### How volatile are sales between periods?
Coefficient of variance 

### Where does the direction point toward?
Understanding the Variables

### How do holidays impact weekly sales?
Impact of Holidays (sales on avg.)

Holiday Differences per year

Sales impact of different holidays

### How do changes in factors like unemployment, cpi and promotional markdowns affect weekly sales changes?
correlation

## 6. Key Feature Candidates
-These are the features I used for the ML Model

## 7. Model Train-Test Split for Forecasting
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
