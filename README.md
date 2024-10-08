# Optimizing Property Valuations: Forecasting Single-Family Home Prices in Connecticut (2006-2021)

## Background and Overview

### Project Context

This project analyzes the Connecticut real estate market, specifically focusing on single-family home sales from 2006 to 2021. The data, provided by the Connecticut Office of Policy and Management (OPM), includes property transactions exceeding $2,000. The goal is to examine trends in home sales, identify the key factors influencing property values, and build a robust predictive model to estimate future sale prices.

The project’s results are intended to serve as a decision-making tool for real estate professionals, investors, and policymakers, enabling them to make informed decisions based on market dynamics, historical trends, and property valuation drivers.

### Main Goal

The primary aim of this project is to develop a model for forecasting single-family home prices in Connecticut. By utilizing historical sales data, the model will uncover patterns and drivers that impact property valuations, offering insights into pricing strategies, investment opportunities, and policy recommendations.

### Key Metrics
The analysis focuses on the following key metrics:

- Year-over-year changes in sale prices and assessed values.
- Sales ratio trends, representing the relationship between assessed value and sale price.
- Key drivers influencing sale prices, including assessed value, market demand, and geographic factors.

### [Data Source](https://catalog.data.gov/dataset/real-estate-sales-2001-2018)

The dataset includes sales data for all real estate transactions in Connecticut where the sale price was greater than $2,000. Key fields include town, property address, sales price, property assessment value, and sales ratio. The dataset covers sales reported between October 1 and September 30 each year, as required by Connecticut General Statutes.

### Tools Used

- Python (Pandas, NumPy, Matplotlib, Seaborn, Skicit-learn) for data cleaning, analysis, and modeling.
- Random Forest Regressor for predictive modeling of sale prices.

## Data Structure Overview

### [Dataset summary](https://data.ct.gov/Housing-and-Development/Real-Estate-Sales-2001-2022-GL/5mzw-sjtu/about_data):


The dataset consists of key columns:

- `list_year`: Year the property was listed for sale.
- `town`: Town where the property is located.
- `assessed_value`: The value used for local tax assessment.
- `sale_amount`: Final sale price of the property.
- `sales_ratio`: Ratio of the sale price to the assessed value.
- `residential_type`: Property type, with a focus on single-family homes for this analysis.
- `non_use_code`: Code indicating if the sale price is considered unreliable for determining property value.
- `opm_remarks`: Notes from OPM that may flag potential data issues, errors, or discrepancies.

During preprocessing, unnecessary columns were removed, such as assessor remarks and non-use code values, to streamline the dataset. Rows with erroneous entries flagged in the OPM remarks were also filtered out. Additionally, outliers in the sales ratio were identified and removed to improve the accuracy and performance of the predictive model. 

Here is sample of the dataset after data preprocessing:

<img src="https://github.com/user-attachments/assets/f544e6fd-3504-4e13-af37-4665d9d3a995" alt="Sample Image" width="500"/>

# Executive Summary

## Key Insights Summary:

### Geographic Pricing Trends:
- The most expensive town for single-family homes is **Greenwich**, with an average sale price of **$2,473,378**.
- The least expensive town is **Windham**, with an average sale price of **$159,641**.
- These findings reflect the economic disparities across Connecticut, with wealthier towns like Greenwich being more desirable due to their proximity to major cities like New York.

<div style="display: flex; justify-content: space-between;">
  <img src="https://github.com/user-attachments/assets/c5951df2-0494-4fce-a5d4-6b6adc552c7d" alt="Top 10 Most Expensive Towns" width="500"/>
  <img src="https://github.com/user-attachments/assets/fdde367b-695d-4f78-b7d6-49d20a741420" alt="Top 10 Least Expensive Towns" width="500"/>
</div>


### Year-Over-Year Sale Trends:
- Home prices saw a stable pattern from 2006 to 2018, followed by a significant price surge starting in **2019**.
- The **2020 housing boom** led to the highest median sale prices in the dataset, likely driven by pandemic-induced demand for housing.

**Recommended Visualization:**
- Use the **'Median Sale Amount Over Time'** line plot to illustrate how sale prices changed between 2006 and 2020, particularly the sharp rise in 2020.

### Model Performance:
- The **Random Forest Regressor** emerged as the best-performing model with an **R² score of 0.993** and an **RMSE of $56,048**. The model's reliance on assessed value highlights the critical role of this feature in predicting sale prices.

**Recommended Visualization:**
- Add the **'Predicted vs Actual Sale Amount'** scatter plot here to visually demonstrate how well the model aligns with actual values.

### Sales Ratio Decline:
- Sales ratios have steadily declined since **2011**, with a sharp drop in **2020**, indicating homes sold for much higher than their assessed values during the pandemic housing surge.

**Recommended Visualization:**
- Include the **'Median Sales Ratio Over Time'** line plot to visualize how the sales ratio changed over the years, highlighting the sharp drop in 2020.

---

# Insights Deep Dive

## 1. Geographic Price Distribution
- **Quantified Value**: Greenwich tops the list of expensive towns at an average sale price of **$2.47 million**, while Windham is the most affordable at **$159,641**.
- **Business Metric**: Real estate professionals and investors can leverage this data to guide investment strategies, with high-end markets (e.g., Greenwich) offering luxury investment opportunities, while lower-cost areas (e.g., Windham) present potential for more affordable housing investments.
- **Historical Trend**: These pricing disparities have persisted across the dataset, with wealthier, coastal towns like Greenwich maintaining their premium status, and more inland areas like Windham remaining budget-friendly.

**Recommended Visualization:**
- Reuse the **'Top 10 Most Expensive Towns'** and **'Top 10 Least Expensive Towns'** bar charts here for better visualization of geographic trends.

## 2. Sale Prices and Market Trends Over Time
- **Quantified Value**: Median sale prices remained relatively stable from **2006 to 2018** but surged in **2020** to their highest point in the dataset.
- **Business Metric**: The **2020 housing boom**—likely driven by pandemic-related demand—indicates a potential opportunity for real estate agents and investors to capitalize on a still-hot market, but also highlights risks in accurately pricing homes during periods of volatility.
- **Historical Trend**: The flat pricing trends before **2019** suggest a stagnant market, possibly due to economic stability, but the sharp price rise from **2019 to 2020** reflects a major shift in housing demand driven by the pandemic.

**Recommended Visualization:**
- ![image](https://github.com/user-attachments/assets/6623d583-cdee-4c0e-86d6-0b7249006c4e)


## 3. Model Performance and Feature Importance
- **Quantified Value**: The **Random Forest Regressor** outperformed other models with an **R² of 0.993** and an **RMSE of $56,048**.
- **Business Metric**: The model provides a reliable framework for estimating home prices, with the **assessed value** being the most influential feature, driving the majority of the predictions.
- **Historical Trend**: Assessed values remain a key determinant of sale prices in Connecticut's real estate market, but the model struggles with extreme outliers, particularly in luxury property sales.

**Recommended Visualization:**
- ![image](https://github.com/user-attachments/assets/ba135a4d-9fa5-4d3d-be1b-71e37edf2b27)


## 4. Sales Ratio Decline and Market Misalignment
- **Quantified Value**: The **sales ratio** (the ratio of sale price to assessed value) fell dramatically from **2011** onwards, reaching its lowest point in **2020**.
- **Business Metric**: This decline suggests a growing gap between assessed values and actual sale prices, with homes selling for far above their assessments. Real estate professionals must account for this when advising clients on market conditions.
- **Historical Trend**: The sharp drop in **2020** aligns with the housing boom, where rapid price increases outpaced the ability of assessed values to keep up, underscoring the lag in property tax assessments during times of economic volatility.

**Recommended Visualization:**
- ![image](https://github.com/user-attachments/assets/c1ff970f-d99d-45a2-94c2-d9bcc204bf92)


---

# Recommendations

### 1. Improve Municipal Property Assessments:
- Municipalities should consider updating their property assessments more frequently, especially in high-demand markets, to better align assessed values with real-time sale prices. This could enhance tax revenue and ensure more accurate property valuations.

### 2. Optimize Pricing Strategies for Real Estate Agents:
- Real estate agents can use the model to recommend listing prices that are aligned with predicted sale prices. This will help sellers set realistic expectations and lead to quicker transactions with fewer negotiations.

### 3. Targeted Investment in Under-Valued Properties:
- Investors can leverage the insights to identify under-valued properties in towns like **Windham** or **Waterbury**, where sale prices are still low compared to their growth potential. Conversely, caution should be exercised in over-valued markets like **Greenwich**, where sale prices may not reflect long-term investment stability.

### 4. Risk Management for Lenders:
- Mortgage lenders should use the model’s predictions to validate loan applications, reducing the risk of approving loans on over-priced properties. This is particularly important in high-value markets, where sale prices have outpaced assessed values.

---

# Caveats and Assumptions

- **Data Limitations**: The analysis only includes single-family home sales in Connecticut, limiting its generalizability to other regions or property types.
- **Assumptions**: Assessed values were treated as a reliable indicator of a property's baseline worth. Future iterations of the model should include additional features like property size, location, and amenities to improve predictions, especially for luxury homes.
