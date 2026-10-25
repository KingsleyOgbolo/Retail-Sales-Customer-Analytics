# Retail Sales Performance and Customer Behaviour Analysis

### An Interactive Excel Business Intelligence Dashboard Using Power Query and Power Pivot

## Project Overview

This project presents an end-to-end retail sales and customer behaviour analysis using Microsoft Excel, Power Query, and Power Pivot.

The analysis uses the UCI Online Retail dataset, covering transactions from December 2010 to December 2011. The dataset contains over 540,000 transaction records from a UK-based online retail business.

The objective is to transform raw transactional data into meaningful business insights through data cleaning, transformation, data modelling, customer segmentation, and interactive dashboard development.

The project examines sales performance, purchasing patterns, product performance, customer value, and revenue distribution across customer segments.

An interactive Excel dashboard allows users to explore key performance indicators and compare business performance across countries.

<img width="975" height="1256" alt="image" src="https://github.com/user-attachments/assets/5bba3a48-1b5e-487f-b384-f2f337c79d4f" />


## Project Objectives

1. Analyse overall retail sales performance using key business metrics.
2. Examine monthly revenue trends and changes in sales performance.
3. Identify top-performing products and customers.
4. Evaluate customer purchasing frequency and average order value.
5. Segment customers based on spending and purchasing behaviour.
6. Analyse revenue contribution across customer segments.
7. Develop an interactive Excel dashboard to support business decision-making.

## Tools and Technologies

| Tool            | Application                                             |
| --------------- | ------------------------------------------------------- |
| Microsoft Excel | Data analysis, visualisation, and dashboard development |
| Power Query     | Data cleaning, transformation, and preparation          |
| Power Pivot     | Data modelling and analytical calculations              |
| DAX             | KPI measures and business calculations                  |
| PivotTables     | Data aggregation and interactive analysis               |
| PivotCharts     | Sales and customer behaviour visualisation              |
| Excel Slicers   | Interactive country-level filtering                     |

## Dataset

**Source:** UCI Machine Learning Repository — Online Retail Dataset

**Period:** December 2010 – December 2011

**Original Dataset:** Approximately 541,909 transaction records.

**Data Coverage:** Retail transactions involving customers from multiple countries.

**Key Variables:** Invoice number, product description, quantity, invoice date, unit price, customer ID, and country.

Dataset link: https://archive.ics.uci.edu/dataset/352/online+retail

## Data Cleaning and Transformation

### 1. Data Import and Initial Assessment

The UCI Online Retail dataset was imported into Microsoft Excel and processed using Power Query.

The original dataset contained approximately **541,909 transaction records**, covering retail transactions between December 2010 and December 2011.

An initial assessment examined the dataset's structure, data types, missing values, transaction quantities, unit prices, and customer identifiers.

### 2. Data Cleaning

Power Query was used to prepare the dataset for analysis.

The cleaning and preparation process included:

* **Data type validation:** Ensured numerical, date, and text columns used appropriate data types.
* **Missing customer identifiers:** Retained transactions without CustomerID for overall sales analysis while distinguishing them from customer-level analysis.
* **Transaction validation:** Examined quantities and unit prices to distinguish valid sales transactions from returns and other records.
* **Returns handling:** Preserved negative quantities where appropriate to calculate net sales after returns.
* **Text standardisation:** Cleaned and standardised relevant text fields, including country names.
* **Calculated fields:** Created transaction-level values to support revenue calculations and further analysis.

### 3. Analytical Data Preparation

Separate Power Query tables were developed to support different analytical requirements.

| Query                                  | Purpose                                                                                                                        |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| `Retail_Cleaned`                       | Prepared transactional data for further analysis.                                                                              |
| `Retail_Sales_Analysis`                | Analysed transactions with positive quantities and unit prices.                                                                |
| `Retail_Net_Sales_Analysis`            | Calculated net transaction values, incorporating positive sales and negative-quantity returns where unit prices were positive. |
| `Retail_Country_Purchase_Frequency`    | Calculated distinct purchase invoice counts by customer and country.                                                           |
| `Retail_Country_Customer_AOV`          | Calculated customer-level average order value using net sales and purchase frequency.                                          |
| `Retail_Country_Customer_Segmentation` | Classified customers into behavioural segments based on spending and purchase frequency.                                       |

### 4. Net Sales Calculation

Net sales were calculated by multiplying transaction quantity by unit price:

**Transaction Value = Quantity × Unit Price**

Unlike gross sales, the net sales calculation incorporates negative-quantity transactions associated with returns.

The resulting overall net sales figure was approximately **£9.76 million**.

This approach provides a more representative measure of revenue than considering positive sales transactions alone.

### 5. Data Modelling

The prepared tables were loaded into Excel's Data Model using Power Pivot.

Relationships between relevant tables supported country-level filtering, customer analysis, and interactive dashboard functionality.

DAX measures and PivotTables were used to calculate and present key performance indicators, including:

* Net Sales
* Unique Customers
* Purchase Orders
* Average Order Value

### 6. Data Quality Considerations

The analysis distinguishes between overall transaction-level revenue and customer-level metrics.

Transactions without customer identifiers contribute to overall net sales where otherwise valid but cannot be reliably assigned to individual customers or customer segments.

Consequently, customer segmentation results represent the identifiable customer population rather than the entire transaction dataset.

## Customer Segmentation Methodology

### 1. Overview

Customer segmentation was performed to identify differences in purchasing behaviour and customer value.

The analysis classified identifiable customers into four behavioural segments using two key metrics:

* **Net Sales:** Total customer spending after accounting for returns.
* **Purchase Frequency:** Number of distinct purchase invoices associated with each customer.

The segmentation was performed at the customer-country level using Power Query.

This approach enables the dashboard to compare customer behaviour across different geographical markets.

### 2. Segmentation Criteria

Customers were classified using a net sales threshold of **£657.55** and a purchase frequency threshold of **two orders**.

The following segmentation rules were applied:

| Customer Segment                | Net Sales | Purchase Frequency |
| ------------------------------- | --------- | ------------------ |
| High-Value Loyal Customers      | ≥ £657.55 | More than 2 orders |
| High-Value Occasional Customers | ≥ £657.55 | 1–2 orders         |
| Regular Low-Spending Customers  | < £657.55 | More than 2 orders |
| Low-Engagement Customers        | < £657.55 | 1–2 orders         |

Only customer-country records with positive net sales and at least one purchase were included in the segmentation.

The £657.55 threshold is a fixed analytical cutoff used in this project rather than a universally applicable definition of a high-value customer.

### 3. Customer Segment Descriptions

**High-Value Loyal Customers**

Customers who generate relatively high net sales and purchase frequently.

These customers are particularly important because they combine strong spending with repeated purchasing activity.

**High-Value Occasional Customers**

Customers who generate relatively high net sales but purchase infrequently.

They may represent opportunities for targeted retention campaigns and repeat-purchase incentives.

**Regular Low-Spending Customers**

Customers who purchase frequently but generate relatively low net sales.

They may respond to product recommendations, cross-selling, and initiatives designed to increase average order value.

**Low-Engagement Customers**

Customers who generate relatively low net sales and purchase infrequently.

This segment may benefit from carefully targeted re-engagement campaigns.

### 4. Segmentation Implementation

The segmentation workflow was developed using Power Query.

The process involved:

1. Aggregating net sales by customer and country.
2. Calculating purchase frequency using distinct invoice counts.
3. Combining customer spending and purchase frequency.
4. Applying conditional segmentation rules.
5. Loading the resulting customer segmentation table into the Excel Data Model.
6. Connecting the segmentation analysis to the dashboard's Country Slicer.

The dashboard presents customer segmentation through two interactive visualisations:

* **Customer Distribution by Segment:** Shows the distinct number of customers with

## Key Business Findings and Insights

### 1. Overall Sales Performance

The analysis revealed approximately **£9.76 million in net sales** during the reporting period, after accounting for negative-quantity transactions associated with returns.

The positive-sales dataset generated approximately **£10.66 million**, highlighting the importance of distinguishing positive transaction values from net sales.

**Business insight:** Reporting net sales alongside positive sales provides a more complete picture of retail performance and the financial effect of returns.

### 2. Customer Behaviour and Purchasing Patterns

Customer purchasing behaviour was evaluated using three key measures:

* **Net Sales:** The total revenue attributable to customers.
* **Purchase Frequency:** The number of distinct purchase invoices.
* **Average Order Value (AOV):** Customer net sales divided by purchase frequency.

The analysis enables comparisons between customers who generate high overall revenue, those who purchase frequently, and those who place high-value orders.

**Business insight:** High purchase frequency does not necessarily indicate high average order value. Businesses should consider multiple customer metrics when identifying valuable customers.

### 3. Customer Segmentation Results

The customer segmentation analysis identified four behavioural groups based on spending and purchasing frequency.

The following results were obtained from the overall customer segmentation analysis:

| Customer Segment                |     Net Sales (£) | Revenue Contribution |
| ------------------------------- | ----------------: | -------------------: |
| High-Value Loyal Customers      |     £7,091,256.52 |                85.3% |
| Low-Engagement Customers        |       £549,129.17 |                 6.6% |
| High-Value Occasional Customers |       £537,964.11 |                 6.5% |
| Regular Low-Spending Customers  |       £134,945.15 |                 1.6% |
| **Total Segmented Revenue**     | **£8,313,294.95** |             **100%** |

*Percentages are rounded to one decimal place.*

### 4. High-Value Loyal Customers Dominate Segmented Revenue

High-Value Loyal Customers contributed approximately **85.3% of total segmented revenue**, making them the most financially significant customer group in this analysis.

This suggests that revenue is highly concentrated among customers who combine relatively high spending with frequent purchasing.

**Business insight:** Customer retention initiatives should prioritise this segment because changes in its purchasing behaviour could materially affect revenue.

### 5. Opportunities Among Other Customer Segments

The remaining customer segments contribute approximately 14.7% of segmented revenue.

Each segment presents different business opportunities:

**High-Value Occasional Customers:** Encourage repeat purchases through targeted communication, personalised recommendations, and loyalty incentives.

**Regular Low-Spending Customers:** Explore cross-selling and product-bundling strategies to increase spending per order.

**Low-Engagement Customers:** Evaluate targeted re-engagement campaigns while considering the cost of acquiring additional purchases.

### 6. Country-Level Analysis

The dashboard includes an interactive Country Slicer, allowing users to examine sales performance and customer behaviour across geographical markets.

Users can explore:

* Net sales by selected country.
* Customer counts and purchase activity.
* Top-performing products and customers.
* Customer segment distribution.
* Revenue contribution by customer segment.

**Business insight:** Country-level filtering supports market comparisons and helps identify differences in purchasing behaviour across geographical locations.

### 7. Interpretation and Limitations

Overall net sales and segmented revenue represent different analytical populations and should not be interpreted as directly equivalent.

Overall net sales include qualifying transactions without customer identifiers, while customer segmentation focuses on identifiable customers meeting the segmentation criteria.

The customer segmentation results are descriptive and do not establish that a particular marketing intervention will increase sales.

The analysis provides a foundation for further investigation and evidence-based business recommendations.

