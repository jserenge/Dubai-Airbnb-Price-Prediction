# 🏠 Dubai Airbnb Data Analysis

## 📌 Overview
This project analyzes Dubai Airbnb listings using a dataset containing **13,560 entries** and **53 features**. The analysis includes **data cleaning, exploratory data analysis (EDA), feature engineering, and machine learning modeling** to predict **average daily rates (ADR)** and identify key factors affecting pricing.

## 📂 Dataset Information
The dataset consists of the following categories:
- **Listing Details:** Property type, listing type, creation date, and location.
- **Pricing & Revenue:** Average daily rate, cleaning fees, extra guest fees, annual revenue.
- **Host & Booking Information:** Superhost status, number of reviews, reservation days, and occupancy rates.
- **Ratings:** Communication, cleanliness, check-in experience, value ratings, etc.

## 🔧 Data Cleaning
- **Handled Missing Values:**
  - Mode imputation for categorical variables (e.g., cancellation policy, superhost status).
  - Mean imputation for numerical variables (e.g., ratings, pricing features).
- **Standardized Columns:**
  - Converted bedroom counts (e.g., "Studio" → `0`).
  - Shortened and standardized cancellation policy names.
- **Dropped Irrelevant Columns:**
  - Removed features like `picture_url`, `license`, `exact_location`, and `last_scraped_date`.

## 📊 Exploratory Data Analysis (EDA)
### Key Insights:
- **Top Listing Types:**
  - Majority are entire rental units, followed by private and shared rooms.
- **Pricing Trends:**
  - High correlation between `bedrooms`, `bathrooms`, and `ADR`.
  - Listings with **more guests allowed** have higher **ADR**.
- **Booking Trends:**
  - Higher occupancy rates lead to higher revenue.
  - Properties with **instant booking enabled** tend to have better ADR.
- **Cancellation Policies:**
  - Most properties follow **"Strict with Grace Period"** policy.
- **Popular Amenities:**
  - Beachfront, private pools, and BBQ areas are associated with **higher ADR**.

## 📈 Feature Engineering
- **Created new features:**
  - `price_per_guest` = `ADR / max_guests`
  - `total_ratings` = sum of all rating scores
  - Extracted date components from `created_date`

## 🤖 Machine Learning Models
### Models Evaluated:
1. **Linear Regression** (Baseline)
   - `MSE: 9659.55, R²: 0.78`
2. **Random Forest Regressor** (Best Model)
   - `MSE: 1892.58, R²: 0.96`
3. **Neural Network (MLP Regressor)**
   - `MSE: 5498.47, R²: 0.87`

### Top Features Affecting ADR:
- 🏡 **Bedrooms & Bathrooms** (Higher counts = higher ADR)
- 📍 **City Location** (Premium areas = higher ADR)
- 🏆 **Superhost Status** (Slightly increases ADR)
- 🎯 **Occupancy Rate & Reservation Days** (Higher demand = higher ADR)

## 📌 Deployment & Usage
### Installation
```bash
pip install -r requirements.txt
```
### Running the Model
```bash
streamlit run app.py
```

## 📅 Future Improvements
- 📊 **Improve feature selection & tuning**
- 🌍 **Integrate real-time Airbnb API for up-to-date analysis**
- 🤖 **Enhance predictive modeling using advanced deep learning**

🚀 **Data-driven insights for smarter Airbnb investments!**

