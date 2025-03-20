# Police shootings analysis

The original file is located at this [link](https://colab.research.google.com/github/pboric/Capstone1/blob/main/capstone_1.ipynb).

## Author 

Petar Krešimir Borić

## 1. Data Cleaning and Preprocessing

### 1.1. Initial Data Inspection

The necessary packages and libraries are installed. The dataset is loaded and an initial exploration is performed to understand the structure, types of data, and any immediately visible inconsistencies (missing values, incorrect data types, etc.).

### 1.2. Handling Missing Data

The **date** column is of type object, which suggests it might need to be converted to datetime for time series analysis. There are missing values in several columns, notably in **county**, **latitude**, **longitude**, **location_precision**, **race**, and **race_source**. The **county**, **race_source**, **name**, **longitude**, **latitude**, **location_precision** features are removed, then missing **ages** are imputed using the **median age**, and the rest of the missing values are imputed with ''Unknown''.

### 1.3. Feature Engineering

**Date-Time Features**: Year, month, day, and weekday are extracted from the 'date' column to analyze temporal trends.

**Location Features**: 'City' and 'state' are combined into a single location feature for simplicity.

**Age Group**: 'Age' is categorized into groups (e.g., minor, adult) for demographic analysis.

## 2. Exploratory Data Analysis (EDA)

### 2.1. Descriptive Statistics

Basic statistical measures (mean, median, mode, quartiles, variance, standard deviation) for quantitative features like age are computed. For categorical data like race or gender, frequency counts are calculated.

### 2.2. Temporal Analysis

Trends over time (yearly, monthly) are analyzed to identify any patterns or spikes in incidents.

### 2.3. Demographic Analysis

The distribution of incidents by age, race, gender, and whether mental illness was related are explored.

### 2.4. Geographical Analysis

Incidents are analyzed by state or region to identify areas with higher occurrences.

## 3. Hypothesis Testing and Inference

Hypothesis based on the EDA and statistical tests to validate them are performed.

### 3.1. Hypothesis: The number of police shootings has increased over the years.

A Generalized Additive Model (GAM) with the independent variable as ‘Months Since Start’ and the dependent variable as ‘Number of Shootings’ is used for the statistical test.

## 4. Predictive analysis

### 4.1 Predict the number of police shootings for the year 2024 using Random Forest model

The number of police shootings for the year 2024 is predicted using a Random Forest model.
