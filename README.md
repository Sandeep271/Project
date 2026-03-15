# MSCS_634_Project_1

## Repository Link
https://github.com/Sandeep271/Project


## Project Deliverable 1: Data Collection, Cleaning, and Exploration

### Student
Sandeep Parupalli

### Course
2026 Spring - Advanced Big Data and Data Mining (MSCS-634-B01)

### Instructor
Satish Penmatsa

## Dataset
This deliverable uses the **Online Retail** dataset from the **UCI Machine Learning Repository**. The original dataset contains **541,909 rows** and **8 columns**:
- InvoiceNo
- StockCode
- Description
- Quantity
- InvoiceDate
- UnitPrice
- CustomerID
- Country

The dataset was selected because it exceeds the minimum assignment requirement, includes both numerical and categorical attributes, and is suitable for later regression, classification, clustering, and pattern mining.

## Major Data Cleaning Steps
The following cleaning steps were completed:
- Removed rows with missing `Description`
- Removed rows with missing `CustomerID`
- Removed duplicate rows
- Removed rows with invalid `Quantity` values (`<= 0`)
- Removed rows with invalid `UnitPrice` values (`<= 0`)
- Created:
  - `TotalSales`
  - `LogTotalSales`
  - `Month`

## Key Findings from Exploration
- Transaction spending was highly right-skewed, with many small purchases and a smaller number of very large purchases.
- A log transformation produced a more balanced spending distribution.
- Monthly sales increased noticeably in the later months, with stronger sales in months 10, 11, and 12.
- The United Kingdom dominated total sales by a wide margin.
- The cleaned dataset provides a strong foundation for later customer-level modeling.

## Challenges and How They Were Addressed
- **Missing values:** Rows missing key fields such as `Description` and `CustomerID` were removed.
- **Duplicate records:** Duplicate rows were identified and removed to prevent inflated counts.
- **Noisy or invalid values:** Nonpositive `Quantity` and `UnitPrice` values were removed.
- **Skewed distributions:** A log transformation was used to improve interpretability of sales distributions.

## Files Included
- `MSCS_634_Project.ipynb`
- `Online Retail.xlsx`
- `Sandeep_Parupalli_Project_Deliverable_1_APA7.docx`

## Source
UCI Machine Learning Repository. (n.d.). *Online retail data set*. https://archive.ics.uci.edu/