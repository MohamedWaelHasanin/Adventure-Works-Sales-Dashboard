# Adventure-Works-Sales-Dashboard
Project Overview
This project demonstrates an end-to-end Extract, Transform, and Load (ETL) pipeline using Power Query. Based on the widely recognized AdventureWorks dataset, this project showcases the ability to ingest raw CSV files, clean and shape the data, consolidate multiple fact tables, and build a robust, analysis-ready data model.

The final output is a clean star schema designed to answer critical business questions regarding sales performance, customer demographics, and product returns.

Data Sources
The raw data consists of several CSV files acting as dimensional lookup tables and a folder of sales fact data:

Product Lookup, Categories, & Subcategories: Detailed hierarchy and cost/pricing data.

Customer Lookup: Demographics and contact information.

Territory Lookup: Geographic sales regions.

Calendar Lookup: Raw dates used to build a dynamic date dimension.

Returns Data: Fact table logging product returns.

Sales Data Folder: Multiple CSV files containing transactional sales data.

ETL Workflow & Transformations
The data preparation was executed entirely in Power Query, heavily utilizing data profiling, custom columns, text extraction, and table merges.

Dimension Table Preparation
Product Dimension: Promoted headers, enforced correct data types (Currency for Cost/Price), extracted "SKU Type" using text delimiters, handled null values, and added calculated columns for a 10% Discount and Discount Amount.

Customer Dimension: Removed errors, standardized names using Proper Case, merged Prefix, First, and Last names into a single Full Name column, and cleanly extracted/capitalized email domains for segmentation.

Calendar Dimension: Built a comprehensive Date Dimension from a base date column, deriving Day Name, Start of Week/Month/Quarter/Year, Month Name, Month Number, and Year.

Territory, Categories & Subcategories: Cleaned, formatted, and validated hierarchy links to ensure seamless relationship building in the final model.

Fact Table Consolidation
Sales Fact Table: Loaded and combined multiple files from a local folder using a custom transformation function. Removed system columns, added a conditional Quantity Type column (Single vs. Multiple Items), and merged with Product, Category, and Subcategory tables to denormalize essential attributes before final cleanup.

Returns Fact Table: Cleaned and structured to easily relate to the Product, Territory, and Calendar dimensions for return rate analysis.

Dashboard Thinking: Analytical Questions
Based on this optimized data model, the final objective is to feed the data into a BI tool (like Power BI) to drive business intelligence. Here are the core analytical questions the resulting dashboard is designed to answer:

Revenue Trends: How do total sales and profitability trend month-over-month and year-over-year?

Product Performance: Which product categories and subcategories drive the highest volume versus the highest profit margins?

Return Analysis: Which specific product SKUs or styles have the highest return rates, and how does this impact overall profitability?

Customer Lifetime Value: Who are the top 20 most valuable customers, and what email domains are most common among them?

Geographic Hotspots: Which regions and countries consistently hit sales targets, and which are underperforming?

Discount Impact: Do sales involving the 10% discount result in higher overall order volumes (Multiple Items vs. Single Item)?

Basket Size: What percentage of transactions consist of single items versus multiple items, and how does that vary by product category?

Tools Used
Power Query / M Code: Data extraction, cleansing, transformation, folder consolidation, and functional formatting.

Data Modeling: Star schema design, dimension-to-fact relationships.
