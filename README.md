# Optimizing Property Valuations: Forecasting Single-Family Home Prices in Connecticut (2006-2021)

## Background and Overview

### Project Context
This project analyzes the Connecticut real estate market, specifically focusing on single-family home sales from **2006 to 2021**. The data, provided by the Connecticut Office of Policy and Management (OPM), includes property transactions exceeding **$2,000**. The goal is to examine trends in home sales, identify the key factors influencing property values, and build a robust predictive model to estimate future sale prices.

The project’s results are intended to serve as a decision-making tool for real estate professionals, investors, and policymakers, enabling them to make informed decisions based on market dynamics, historical trends, and property valuation drivers.

### Main Goal
The primary aim of this project is to develop a model for forecasting single-family home prices in Connecticut. By utilizing historical sales data, the model will uncover patterns and drivers that impact property valuations, offering insights into pricing strategies, investment opportunities, and policy recommendations.

### Key Metrics
The analysis focuses on the following key metrics:

- Year-over-year changes in sale prices and assessed values.
- Sales ratio trends, representing the relationship between assessed value and sale price.
- Key drivers influencing sale prices, including assessed value, market demand, and geographic factors.

### [Data Source](https://catalog.data.gov/dataset/real-estate-sales-2001-2018)
The dataset includes sales data for all real estate transactions in Connecticut where the sale price was greater than **$2,000**. Key fields include town, property address, sales price, property assessment value, and sales ratio. The dataset covers sales reported between October 1 and September 30 each year, as required by Connecticut General Statutes.

### Tools Used
- Python (Pandas, NumPy, Matplotlib, Seaborn, Skicit-learn) for data cleaning, analysis, and modeling.
- Random Forest Regressor for predictive modeling of sale prices.

---

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

  <img src="https://github.com/user-attachments/assets/f544e6fd-3504-4e13-af37-4665d9d3a995" alt="Sample Image" width="600"/>

## Executive Summary

### Key Insights Summary:
#### Geographic Pricing Trends:
- The most expensive town for single-family homes is **Greenwich**, with an average sale price of **$2,473,378**.
- The least expensive town is **Windham**, with an average sale price of **$159,641**.
- These findings reflect the economic disparities across Connecticut, with wealthier towns like Greenwich likely being more desirable due to their proximity to major cities like New York.

<div style="display: flex; justify-content: space-between;">
  <img src="https://github.com/user-attachments/assets/c5951df2-0494-4fce-a5d4-6b6adc552c7d" alt="Top 10 Most Expensive Towns" width="600"/>
  <img src="https://github.com/user-attachments/assets/fdde367b-695d-4f78-b7d6-49d20a741420" alt="Top 10 Least Expensive Towns" width="600"/>
</div>

#### Year-Over-Year Sale Trends:
- Home prices saw a relatively stable pattern from **2006 to 2018**, with a **15% overall decrease** in median sale prices during this period. This suggests a stagnant market likely due to the lingering effects of the 2008 financial crisis.
- However, starting in **2019**, a significant price surge began, with a **18% increase** in median sale prices from 2019 to 2020, reflecting the impact of the **2020 housing boom** likely driven by pandemic-induced demand for housing.

    <img src="https://github.com/user-attachments/assets/58843984-e54a-44dd-8fee-a8b50f0e468a" alt="" width="600"/>

#### Model Performance:
- The **Random Forest Regressor** was the top-performing predictive model, achieving great scores. Specifically, the metrics suggest that the model can explain 99.3% of the variability in sale prices, with an average prediction error of about $56,000. The model's strong reliance on **assessed value** as a key feature highlights its importance in predicting home prices.


    <img src="https://github.com/user-attachments/assets/9f962b92-b5dc-48d1-98cf-cb79f1de17ec" alt="" width="600"/>

#### Sales Ratio Decline:
- Sales ratios have steadily declined since **2011**, with a sharp **35% decrease** from 2011 to 2021. The most notable drop occurred in **2020**, where the sales ratio fell by **13%**, indicating that homes were selling far above their assessed values during the pandemic housing surge.


    <img src="https://github.com/user-attachments/assets/c92e28cb-e9bb-4cb1-b298-1508cfdc765e" alt="" width="600"/>


---

## Insights Deep Dive

### 1. Geographic Price Distribution
- **Quantified Value**: Greenwich tops the list of expensive towns at an average sale price of **$2.47 million**, while Windham is the most affordable at **$159,641**.
- **Business Metric**: Real estate professionals and investors can leverage this data to guide investment strategies, with high-end markets (e.g., Greenwich) offering luxury investment opportunities, while lower-cost areas (e.g., Windham) present potential for more affordable housing investments.
- **Historical Trend**: These pricing disparities have persisted across the dataset, with wealthier, coastal towns like Greenwich maintaining their premium status, and more inland areas like Windham remaining budget-friendly.

### 2. Sale Prices and Market Trends Over Time
- **Quantified Value**: Median sale prices remained relatively stable from **2006 to 2018**, with a **15% decrease** in sale prices over this period. However, from **2019 to 2020**, prices surged, with an **18% increase**, reflecting the rapid rise in housing demand during the pandemic.
- **Business Metric**: The **2020 housing boom**—likely driven by pandemic-related demand—indicates a potential opportunity for real estate agents and investors to capitalize on a still-hot market, but also highlights risks in accurately pricing homes during periods of volatility.
- **Historical Trend**: The flat pricing trends before **2019** suggest a stagnant market, possibly due to economic stability, but the sharp price rise from **2019 to 2020** reflects a major shift in housing demand driven by the pandemic.

    <img src="https://github.com/user-attachments/assets/6623d583-cdee-4c0e-86d6-0b7249006c4e" alt="" width="600"/>

### 3. Model Performance and Feature Importance
- **Quantified Value**: After testing several models, the **Random Forest Regressor** proved to be the most accurate, achieving an **R² of 0.993** and an **RMSE of $56,048**. This means that the model is able to explain 99.3% of the variation in home prices, with the average error in its predictions being around $56,048. In simple terms, the model does a great job of predicting home prices, but you can expect its estimates to be off by about $56,000 on average.
- **Business Metric**: The model serves as a reliable tool for estimating home prices, with the **assessed value** being the most important factor driving its predictions. This means that how homes are valued by assessors plays a key role in determining their sale price.
- **Historical Trend**: The model confirms that **assessed values** continue to be a major factor in predicting home sale prices in Connecticut. However, it has trouble accurately predicting prices for very expensive homes (luxury properties), where the predictions may not be as precise.


### 4. Sales Ratio Decline and Market Misalignment
- **Quantified Value**: The **sales ratio** (ratio of sale price to assessed value) fell dramatically, with a **35% decrease** from its peak in **2011** to its lowest point in **2021**. The sharpest decline occurred in **2020**, where the sales ratio dropped by **13%** compared to the previous year.
- **Business Metric**: This decline suggests a growing gap between assessed values and actual sale prices, with homes selling for far above their assessments. Real estate professionals must account for this when advising clients on market conditions.
- **Historical Trend**: The sharp drop in **2020** aligns with the housing boom, where rapid price increases outpaced the ability of assessed values to keep up, highlighting the lag in property tax assessments during times of economic volatility.

---

##  Recommendations

#### 1. Improve Municipal Property Assessments:
- Municipalities should consider updating their property assessments more frequently, especially in high-demand markets, to better align assessed values with real-time sale prices. This could enhance tax revenue and ensure more accurate property valuations.

#### 2. Optimize Pricing Strategies for Real Estate Agents:
- Real estate agents can use the model to recommend listing prices that are aligned with predicted sale prices. This will help sellers set realistic expectations and lead to quicker transactions with fewer negotiations.

#### 3. Targeted Investment in Under-Valued Properties:
- Investors can leverage the insights to identify under-valued properties in towns like **Windham** or **Waterbury**, where sale prices are still low compared to their growth potential. Conversely, caution should be exercised in over-valued markets like **Greenwich**, where sale prices may not reflect long-term investment stability.

#### 4. Risk Management for Lenders:
- Mortgage lenders should use the model’s predictions to validate loan applications, reducing the risk of approving loans on over-priced properties. This is particularly important in high-value markets, where sale prices have outpaced assessed values.

---

## Caveats and Assumptions

- **Data Limitations**: The analysis only includes single-family home sales in Connecticut, limiting its generalizability to other regions or property types.
- **Assumptions**: Assessed values were treated as a reliable indicator of a property's baseline worth. Future iterations of the model should include additional features like property size, location, and amenities to improve predictions, especially for luxury homes.
