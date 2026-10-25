# Retail Sales Performance and Customer Behaviour Analysis

### An Interactive Excel Business Intelligence Dashboard Using Power Query and Power Pivot

## Project Overview

This project presents an end-to-end retail sales and customer behaviour analysis using Microsoft Excel, Power Query, and Power Pivot.

The analysis uses the UCI Online Retail dataset, covering transactions from December 2010 to December 2011. The dataset contains over 540,000 transaction records from a UK-based online retail business.

The objective is to transform raw transactional data into meaningful business insights through data cleaning, transformation, data modelling, customer segmentation, and interactive dashboard development.

The project examines sales performance, purchasing patterns, product performance, customer value, and revenue distribution across customer segments.

An interactive Excel dashboard allows users to explore key performance indicators and compare business performance across countries.

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

