# Northwind Sales Performance Analysis

## Project Overview

This project conducts an exploratory data analysis (EDA) of sales transaction data extracted from the classic **Northwind Traders sample database**. Utilizing PostgreSQL for data extraction and R for analysis and visualization, the primary goal is to uncover key sales trends, identify top-performing products and categories, and understand temporal (seasonal) patterns in customer purchasing behavior.

The insights derived from this analysis aim to provide actionable business intelligence for optimizing inventory, refining marketing strategies, and enhancing overall sales efficiency for a simulated retail environment.

## Problem Statement & Analytical Questions

To gain a comprehensive understanding of Northwind's sales dynamics, this analysis addresses the following core questions:

1.  **What are the best-selling products and categories?**
    * Identifying the primary revenue drivers at both granular (product) and aggregated (category) levels.
2.  **Are there seasonal trends in sales?**
    * Examining annual and monthly sales performance to detect periods of peak demand and understand temporal fluctuations.
3.  **What are the average order sizes, and do they vary over time?**
    * Investigating customer purchasing behavior by analyzing the typical quantity of items ordered per transaction and its consistency or variation across different periods.

## Data Source

The dataset used for this analysis was extracted from the **Northwind sample database**, specifically focusing on sales-related tables. The extraction was performed using **PostgreSQL**.

The key columns utilized in this analysis include:
* `order_date`: Date of the sales transaction.
* `year`: Year of the order (derived).
* `month`: Month of the order (derived).
* `product_name`: Name of the individual product.
* `category_name`: Product category.
* `unit_price`: Price per unit at the time of order.
* `order_quantity`: Number of units ordered in a transaction.

## Methodology & Analysis

The project employs a structured EDA approach using R, leveraging the `tidyverse` suite of packages for data manipulation and `ggplot2` for visualization.

1.  **Data Extraction & Preparation:**
    * Data was pulled from PostgreSQL.
    * Necessary columns were selected, and `year` and `month` variables were derived from `order_date`.
    * `total_revenue` was calculated for each transaction (`unit_price * order_quantity`).
2.  **Top Products & Categories Analysis:**
    * Aggregated `total_revenue` by `category_name` and `product_name`.
    * Identified and visualized the top-performing categories and the top 20 products by revenue.
3.  **Seasonal Trend Analysis:**
    * Calculated and visualized total revenue by `year`, `month`, and `year-month` combinations.
    * Examined the top products and categories on an annual basis to observe consistency or shifts in their dominance over time.
4.  **Average Order Size Analysis:**
    * Calculated and visualized the average `order_quantity` by `year` and `month`.
    * Used box plots to understand the distribution and variability of order sizes across years.

## Key Findings & Insights

### 1. Revenue Drivers:
* **Categories:** **Beverages, Dairy Products, and Meat/Poultry** are consistently the top three revenue-generating categories, forming the core of Northwind's sales.
* **Products:** **Côte de Blaye** stands out as the single highest-revenue product, significantly contributing to the overall sales figures. Other key contributors include Thüringer Rostbratwurst, Rössle Sauerkraut, and Camembert Pierrot.

### 2. Seasonal & Annual Trends:
* **Annual Peak:** **1997** was Northwind's strongest year in terms of total revenue.
* **Seasonal Peak:** There is a clear and consistent **Q4 (October, November, December) sales surge**, with **December** being the highest-performing month. This indicates significant seasonal demand, likely tied to holiday purchasing.
* **Evolving Dominance:** While core categories generally remain strong, their precise rankings and the specific top-performing products can exhibit slight shifts year-over-year, necessitating continuous monitoring.

### 3. Order Size Dynamics:
* **Consistency:** The **average order size remains remarkably stable at approximately 23-24 units annually**, suggesting consistent customer purchasing behavior.
* **Seasonal Nuance:** Average order size experiences a **slight but notable increase during peak months (e.g., December)**, indicating customers not only order more frequently but also purchase slightly larger quantities per transaction during these periods.

## Business Recommendations

Based on these findings, Northwind Traders can implement the following strategies:

* **Prioritize Top Categories & Products:** Ensure robust inventory management and focused marketing efforts for Beverages, Dairy Products, Meat/Poultry, and individual high-value items like Côte de Blaye. These are the "cash cows" of the business.
* **Optimize for Q4:** Allocate a disproportionately higher share of marketing spend and operational resources (inventory, staffing, logistics) to Q4. Develop targeted campaigns that encourage larger basket sizes during this period, leveraging the observed increase in average order quantity.
* **Strategic Off-Peak Initiatives:** Explore promotions, bundles, or loyalty programs during slower months (e.g., Q3) to smooth out demand and maintain revenue consistency year-round.
* **Refine Forecasting:** Integrate the identified seasonal patterns and stable average order size into more precise sales forecasting models for improved inventory planning and resource allocation.
* **Explore Upselling/Cross-selling:** Capitalize on the stable average order size by introducing specific upselling techniques or product bundles, especially in top-performing categories, to gently nudge customers towards larger purchases.

## Technologies & Tools

* **R Programming Language:** Core for data analysis and visualization.
* **RStudio / VS Code:** Integrated Development Environment (IDE).
* **`tidyverse` (dplyr, ggplot2):** For data manipulation and high-quality visualizations.
* **`RPostgres`:** For connecting to and querying the PostgreSQL database.
* **`knitr` / Quarto:** For reproducible reporting and rendering to HTML.
* **PostgreSQL:** Relational database for data storage and extraction.
* **Git & GitHub:** For version control and project hosting.

## How to Reproduce This Analysis

To reproduce this analysis locally, please follow these steps:

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/your-username/northwind_sales_analysis.git](https://github.com/your-username/northwind_sales_analysis.git)
    cd northwind_sales_analysis
    ```
2.  **Database Setup:**
    * Ensure you have a PostgreSQL instance running with the Northwind sample database loaded.
    * Set up your database credentials as environment variables. Create a `.Renviron` file in the project root (and ensure it's in your `.gitignore`!):
        ```
        PG_DB=your_database_name
        PG_HOST=localhost
        PG_USER=your_username
        PG_PASSWORD=your_password
        ```
    * **Restart your R session** after creating/editing `.Renviron`.
3.  **Install R Packages:**
    * Open the `northwind_sales_analysis.Rproj` file in RStudio or open the project folder in VS Code with the R extension.
    * Install the necessary R packages:
        ```R
        install.packages(c("DBI", "RPostgres", "tidyverse", "ggplot2", "knitr"))
        ```
4.  **Run the Analysis:**
    * Open `reports/northwind_sales_analysis.Rmd` (or `.qmd` if you are using Quarto).
    * Click the "Knit" button (in RStudio) or use the appropriate command in VS Code to render the report to HTML. This will execute all the R code and generate the final report in the `reports/` directory.

## Contact

Namshima B. Iordye


iordyebarnabas12@gmail.com
---
