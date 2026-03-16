# Project Deliverable 1

## Repository Link
https://github.com/Sandeep271/Project

## Course Information
**Student:** Sandeep Parupalli  
**Course:** 2026 Spring - Advanced Big Data and Data Mining (MSCS-634-B01)  
**Instructor:** Satish Penmatsa  

## Deliverable Scope
This repository contains the materials for **Project Deliverable 1** only. The scope of this deliverable is limited to dataset selection, data cleaning, and exploratory data analysis using the Online Retail dataset.

## Dataset Summary
This deliverable uses the **Online Retail** dataset from the **UCI Machine Learning Repository**. The original dataset contains **541,909 rows** and **8 columns**:

- InvoiceNo
- StockCode
- Description
- Quantity
- InvoiceDate
- UnitPrice
- CustomerID
- Country

The dataset was selected because it is large enough for meaningful analysis, includes both numerical and categorical variables, and provides a strong foundation for later modeling tasks.

## Major Data Cleaning Steps
The notebook performs the following cleaning steps:

- removed duplicate rows
- removed rows with missing `Description`
- removed rows with missing `CustomerID`
- removed rows with invalid `Quantity` values (`<= 0`)
- removed rows with invalid `UnitPrice` values (`<= 0`)
- created the following derived variables:
  - `TotalSales`
  - `LogTotalSales`
  - `Month`

## Key Insights from Exploration
- Transaction spending is highly right-skewed, with many small purchases and a smaller number of very large purchases.
- A log transformation produces a more balanced spending distribution.
- Monthly sales are stronger in the later months of the year, especially in months 10, 11, and 12.
- The United Kingdom contributes the largest share of total sales by a wide margin.
- The cleaned dataset provides a solid basis for later phases of the project.

## Challenges and How They Were Addressed
- **Missing values:** Rows missing key fields such as `Description` and `CustomerID` were removed because they reduced interpretability.
- **Duplicate records:** Exact duplicates were removed to avoid inflated counts and misleading summaries.
- **Invalid transaction values:** Nonpositive `Quantity` and `UnitPrice` values were removed for cleaner sales analysis.
- **Skewed sales distribution:** A log transformation was added to make the distribution easier to interpret.

## Files Included
- `MSCS_634_Project_Deliverable_1_Submission_Ready.ipynb`
- `README.md`
- `Sandeep_Parupalli_Project_Deliverable_1_APA7_Submission_Ready.docx`

## Source
UCI Machine Learning Repository. (n.d.). *Online retail data set*.
