# GTC ML Project 1 - Hotel Bookings Data Preprocessing

## Project Overview
This project focuses on preparing a hotel booking dataset for a machine learning model that predicts booking cancellations.  
The revenue team identified that last-minute cancellations significantly impact profitability, so the goal is to clean, preprocess, and create ML-ready features for modeling.

## Dataset
- File: `hotel_bookings.csv`
- Source: Property Management System (PMS)
- Contains: Hotel bookings information such as guest counts, stay duration, booking details, payment info, and more.

## Project Phases

### Phase 1: Exploratory Data Analysis (EDA)
- Loaded the dataset using Pandas.
- Checked for missing values and visualized their patterns.
- Detected outliers in numerical columns (`adr`, `lead_time`) using boxplots and IQR method.
- Documented main data quality issues.

### Phase 2: Data Cleaning
- Handled missing values:
  - `company` and `agent`: replaced with 0 (IDs)
  - `country`: replaced with mode
  - `children`: replaced with mode
- Removed duplicate rows.
- Capped outliers in `adr` to prevent skewing.
- Converted date columns to `datetime` format.

### Phase 3: Feature Engineering & Preprocessing
- Created new features:
  - `total_guests = adults + children + babies`
  - `total_nights = stays_in_weekend_nights + stays_in_week_nights`
  - `is_family = 1` if children or babies, else 0
- Encoded categorical variables:
  - One-Hot Encoding for low-cardinality features (`meal`, `market_segment`, `hotel`)
  - Frequency Encoding for high-cardinality feature (`country`)
- Removed data leakage columns (`reservation_status`, `reservation_status_date`)
- Split dataset into training and testing sets (`test_size=0.2, random_state=42`)

## How to Use
1. Clone this repository.
2. Open `hotel_bookings_preprocessing.ipynb` in Google Colab.
3. Upload the `hotel_bookings.csv` dataset.
4. Run all cells to reproduce data cleaning and preprocessing steps.



## Author
Your Name
Anas Abdelaziz