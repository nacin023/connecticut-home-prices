
# Background and Overview

## Project Context

This project examines the real estate market in Connecticut, focusing on single-family home sales between 2006 and 2021. The data, sourced from the Connecticut Office of Policy and Management (OPM), provides insights into property transactions exceeding $2,000. The primary aim of this analysis is to explore trends in home sales, understand key factors influencing property values, and build a predictive model to estimate future sale prices.

## Main Goal

To develop an approach for forecasting single-family home prices in Connecticut, utilizing historical sales data to identify patterns and drivers of property valuation. This model serves as a tool for real estate professionals, investors, and policymakers to make informed decisions based on market dynamics.

## Key Metrics

- Year-over-year changes in sale prices and assessed values.
- Sales ratio trends, representing the relationship between assessed value and sale price.
- Key drivers influencing sale prices.

## [Data Source](https://catalog.data.gov/dataset/real-estate-sales-2001-2018)

The dataset includes sales data for all real estate transactions in Connecticut where the sale price was greater than $2,000. Key fields include town, property address, sales price, property assessment value, and sales ratio. The dataset covers sales reported between October 1 and September 30 each year, as required by Connecticut General Statutes.

## Tools Used

- Python (Pandas, NumPy, Matplotlib, Seaborn, skicit-learn) for data cleaning, analysis, and modeling.
- Random Forest Regressor for predictive modeling of sale prices.

# Data Structure Overview

The dataset, sourced from the Connecticut Office of Policy and Management, contains real estate sales records from October 1, 2001, through September 30, 2021. Each row represents a property sale, and the dataset includes a total of 14 columns, providing information on the sale amount, assessed value, town, and other important attributes.

## Key Columns

- `list_year`: Year the property was listed for sale.
- `town`: Town where the property is located.
- `assessed_value`: The value used for local tax assessment.
- `sale_amount`: Final sale price of the property.
- `sales_ratio`: Ratio of the sale price to the assessed value.
- `residential_type`: Property type, with a focus on single-family homes for this analysis.
- `non_use_code`: Code indicating if the sale price is considered unreliable for determining property value.
- `opm_remarks`: Notes from OPM that may flag potential data issues, errors, or discrepancies.

During preprocessing, unnecessary columns were removed, such as assessor remarks and non-use code values, to streamline the dataset. Rows with erroneous entries flagged in the OPM remarks were also filtered out. Additionally, outliers in the sales ratio were identified and removed to improve the accuracy and performance of the predictive model. 

