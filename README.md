# Superstore Sales Analysis - Power BI Report 

![Power BI Report Page](https://github.com/taarikakanauji/superstore-sales-analysis/raw/main/images/Power-Bi-report.jpg)

## Problem Statement

Stakeholders across various departments currently lack a centralized, data-driven view to effectively monitor and analyze superstore sales performance across different product categories, geographic regions, time periods, and customer segments. This data gap makes it difficult to identify underperforming categories, evaluate sales trends, and make informed decisions based on critical metrics such as total sales, profit margins, average order value, year-over-year (YoY) sales growth, and sales by state.

The dashboard provides comprehensive, data-driven insights to uncover emerging sales trends, identify areas of revenue growth or decline, and optimize product assortment and regional sales strategies. It empowers decision-makers with an interactive and intuitive interface to monitor category-wise performance, track YoY sales across states, assess profitability, and make informed decisions based on a clear understanding of sales dynamics and regional market behavior.

The Superstore Sales Analysis project is designed for stakeholders who uses a data dashboard to track and understand sales performance. They can look at sales trends over year, different product categories, customer types, and sales across various regions to identify patterns and opportunities for growth. The dashboard will be extremely helpful to multiple stakeholders including: 

- Business Owners & Decision Makers – To track profitability and make strategic decisions.

- Sales & Marketing Teams – To improve product positioning and regional sales.
- Corporate & B2B Clients – For bulk purchasing insights and business opportunities.
- Retail & Inventory Managers – To optimize stock based on sales patterns.

# Objective

`Establish a centralized dashboard` -
Develop a comprehensive and interactive dashboard to provide a unified, real-time view of superstore sales performance across product categories, states, time periods, and customer segments.

`Enhance data-driven decision making` -
Empower stakeholders with actionable insights into key metrics such as total sales, profit, average sales, YoY growth, and sales by region to support both strategic and operational decision-making.

`Enhance sales and profitability` -
Analyze sales patterns and trends, identify underperforming categories or products, and optimize pricing, discounting strategies, and inventory management to drive higher margins and customer satisfaction.

`Optimize product performance across regions` -
Track regional sales performance, control cost drivers such as logistics and marketing spend, and improve gross and net profit margins across states and markets.

`Improve forecasting and demand planning` -
Leverage historical sales data and seasonal trends to enhance forecasting accuracy, reduce stockouts or overstock situations, and streamline supply chain and inventory planning.

## Key Questions

    Q : Which product categories are generating the highest and lowest total sales?

    Q : Are there particular months or seasons where sales spike or drop significantly?

    Q : Which sub-categories or products are consistently underperforming?

    Q : Which states or regions are driving the most revenue?

    Q : How do return rates and profit margins compare across different states?

    Q : What is the average order value across different customer segments or regions?

    Q : How have total sales and profits trended year-over-year (YoY)? 

    Q : Are there any regions with high sales but low profitability?

    Q : What is the average sales per order or per customer across different regions?  

## Steps followed 

As a Business Analyst for a leading retail organization, I led the development of an interactive Superstore Sales Analysis Dashboard designed to equip stakeholders with a unified view of sales performance, product trends, return rates, and key operational metrics across various regions, categories, and customer segments.

The primary goal was to generate actionable insights that would enable data-driven decisions—optimizing product mix, boosting sales and marketing effectiveness, increasing profitability, and aligning cross-functional strategies with performance outcomes.

Below is my step-by-step approach to creating this dashboard in Power BI:

- Step 1 : Upload all csv data files in mySQL work bench. After that, connect it with the Power BI platform using Connector by giving mySQL workbench credentials. Lastly, select the tables from the mySQL database.

- Step 2: Open the Power Query Editor and navigate to the View tab. Enable Column Distribution, Column Quality, and Column Profile under the Data Preview section to gain deeper insights into the structure and quality of the dataset.

- Step 3: By default, Power BI profiles only the first 1000 rows. To perform a more thorough analysis, update the setting to "Column profiling based on entire dataset" to ensure comprehensive data validation.

- Step 4: After reviewing and cleansing the dataset, ensure there are no errors or missing values across any columns. This confirms that the dataset is clean, reliable, and ready for downstream transformations and visualizations.

- Step 5: Switch to the Report View and apply the default theme under the View tab to maintain a consistent and professional visual style across the dashboard.

- Step 6: **Designing KPI Cards for Key Metrics** – To give stakeholders a quick and clear snapshot of overall performance, I designed six KPI cards that showcase critical engagement metrics. These KPIs deliver real-time insights into business activity, enabling swift and informed decision-making.

      
    Total sales = SUM(Orders[Sales])

    Total Quantity = SUM(Orders[Quantity])

    Total profits = SUM(Orders[Profit])

    Sales YoY % = DIVIDE(SUM(Orders[Sales]) - [Previous year sales], [Previous year sales])

    Quantity YoY % = DIVIDE(SUM(Orders[Quantity]) -[Previous Quantity], [Previous Quantity])

    Previous year sales = CALCULATE(SUM(Orders[Sales]),DATEADD(Orders[Order Date].[Date],-1,YEAR))

    Previous Quantity = CALCULATE(SUM(Orders[Quantity]),DATEADD(Orders[Order Date].[Date],-1,YEAR))

    Number of orders = COUNT(Orders[Order ID])

    Number of customers = DISTINCTCOUNT(Orders[Customer ID])

    Average sales = AVERAGE(Orders[Sales])

    Maximum sale = MAX(Orders[Sales])



  All KPI cards were formatted using currency symbols where applicable, enhancing visual clarity and ensuring executives can quickly interpret them without needing to explore detailed datasets.

  ![KPI Highlights](https://github.com/taarikakanauji/superstore-sales-analysis/raw/main/images/kpi.jpg)
           
- Step 7 : **Sales by State** – I incorporated an interactive map to effectively represent the sales for each individual state. 

        Fields Used:

        Location : States


   The sales are also highlighted with a color shade for a quick visual understanding of how high or low the sales may be for that state. The primary benefit of this map is that it gives a state-wide heartbeat of the sales numbers to the viewer.

  ![Sales by Map](https://github.com/taarikakanauji/superstore-sales-analysis/raw/main/images/map.jpg)

- Step 8 : **Sales & Sales YoY% by Year** – I implemented a vertical bar chart to illustrate the trends for the YoY (year-over-year) sum of sales. 

        Fields used:

        X-Axis: Order date, Year

        Y-axis: Sum of Sales 

        Line Yaxis: Sales YoY%

   The chart reveals that 2014 was the highest year in terms of total sales while 2012 was the lowest, which represents a positive uptrend in the overall business. However, the interesting thing is that 2014 showed a decline in terms of YoY% sales compared to 2013, which was reported as the highest.

   There were no massive fluctuations observed in terms of increase or decrease of the sales. This indicates a steady state of the business, and at the same time, untapped potential for further growth through new strategies and products.

  ![YoY Sales Comparison](https://github.com/taarikakanauji/superstore-sales-analysis/raw/main/images/yoy-sales.jpg)

- Step 9 :  **Total Sales by Category** – I created a donut chart to showcase the total sales by categories. This gives us a high-level picture of how the categories are performing.

        Fields used:

        Legends: Category (Technology, Furniture, Office Supplies)

        Values: Sum of Sales

  From the data, it is evident that Technology was the biggest sales driver, followed by Furniture and lastly, Office Supplies. However, the difference between Furniture and Office Supplies is very minimal

  Since Furniture and Office Supplies are relative categories, creative marketing efforts can be put towards upselling office supplies to furniture purchasers and vice-versa.

  ![Sales by Category](https://github.com/taarikakanauji/superstore-sales-analysis/raw/main/images/sales-category.jpg)

- Step 10 : **Total Sales by Sub-Category** - This horizontal bar graph describes the total sales achieved by each of the sub-categories.

        Fields used:

        X-axis: Total Sales

        Y-axis: Sub-category

  From the graph, we can pinpoint that Chairs is the leading sub-category while Storage is the least sales generating. Tables also brings in the same amount of sales as the Storage.

  Contrary to this, Phones and Machines bring in the second and third highest sales, after Chairs. This suggests that Technology is a strong performing category in terms of sales.

    ![Sales by Sub-Category](https://github.com/taarikakanauji/superstore-sales-analysis/raw/main/images/sales-sub-category.jpg)

- Step 11 : **Total Sales by Customer Segment** - This is represented using a Treemap that shows the total sales recorded across the various customer segments such as Consumer, Corporate, and Home Office.

        Fields used:

        Category: Customer Segment (Consumer, Corporate, and Home Office)

        Values: Total Sales

  From this treemap, we can concur that Consumer segment outperforms the other two segments, Corporate and Home Office. In fact, Consumer segment earns almost nearly thrice the amount of Home Office segment. 

  The massive gap between the other segments suggests that either the demand is extremely low and sales are not happening, or the product market fit is not there for the catalogue of products that are being sold under these segments. 

    ![Sales by Segment](https://github.com/taarikakanauji/superstore-sales-analysis/raw/main/images/sales-segment.jpg)

- Step 12 :  **Quantity and Sales YoY% Table** – I created a tabular visualization to showcase the Year, Sum of Quantity, Quantity YoY%, Sum of Sales and Sales YoY% which can help stakeholders to assess the fundamental financials of the business.

        Fields used (Table format):

        Rows:

        Order date, Year

        Values:

        Sum of Quantity: Total number of quantity

        Quantity YoY%: The change in Quantity year-over-year in percentage

        Sum of Sales: The total amount of sales

        Sales YoY%: The change in Sales year-over-year in percentage

  From the table, we can see that 2014 had the highest quantity recorded and also the Sum of sales was the highest in the same year. 

  Considering the YoY% metric, the year 2013 had the best result of 36.85% sales increase compared to previous year. While 2014 had less than 2013, it was still not as low as compared to year 2012 when the Sales YoY% was -9.51%.

  ![Sales Data Table](https://github.com/taarikakanauji/superstore-sales-analysis/raw/main/images/table.jpg)


- Step 13: **Adding Filters to the Dashboard** - To enhance user experience and interactivity, I incorporated two slicers that allow users to tailor the data view based on their preferences. These slicers are easily accessible via a filter icon positioned at the top of the dashboard.

  Setting Up Slicers for Interactive Filtering –
  I set up the slicers to allow users to interact with the report dynamically, enabling them to focus on specific data segments for more detailed analysis. These filters help users drill down into key dimensions for meaningful, context-specific insights.

  I added slicers for:

      Order Date 

      Ship Mode 

      Region

  To ensure a clean and professional design, I utilized dropdown-style slicers that apply to all visuals within the report. This configuration empowers stakeholders to easily compare trends over different time periods or evaluate performance across various regions with minimal effort.

- Step 13: To improve the usability and interactivity of the Power BI report, I added a Reset Filters icon that enables users to quickly clear all selections and revert the report to its original default view. This feature enhances user confidence by making it easy to undo any filter changes, providing more flexibility and a smoother experience.

  First, I inserted a reset or refresh icon using the Insert > Image option and positioned it to the left of the filter icon.

  Next, I manually cleared all filter selections, including Year and Continent name.

  Finally, I enabled the Action feature on the reset icon by setting the Type to Bookmark and linking it to the Clear all Filters bookmark. This configuration ensures that clicking the icon resets all filters to their default (unselected) state.


# Snapshot of Report (Power BI Service)

![Power BI Service View](https://github.com/taarikakanauji/superstore-sales-analysis/raw/main/images/Power-Bi-service-full.jpg)

# Report Snapshot (Power BI DESKTOP)

 ![Full Power BI Report](https://github.com/taarikakanauji/superstore-sales-analysis/raw/main/images/Power-Bi-report-full.jpg)


# **Project Resources: Superstore Sales Analysis**  

### **Detailed Report (PDF)**  
[Insights of Superstore Sales Analysis](https://github.com/taarikakanauji/superstore-sales-analysis/blob/main/Superstore%20Sales%20Analysis.pdf)  

### **Power BI Desktop Demo**  
[Power BI Demo (MKV)](https://github.com/taarikakanauji/superstore-sales-analysis/blob/main/Power-BI-Demo.mkv)  

### **Power BI Service Demo**  
[Power BI Service Demo (MKV)](https://github.com/taarikakanauji/superstore-sales-analysis/blob/main/Power-Service-Demo.mkv)  

### **Dataset Folder**  
[Dataset Files](https://github.com/taarikakanauji/superstore-sales-analysis/tree/main/dataset)  

### **PBIP Files**  
- **Report:** [Report Files](https://github.com/taarikakanauji/superstore-sales-analysis/tree/main/Superstore%20Sales%20Analysis.Report)  
- **Semantic Model:** [Semantic Model Files](https://github.com/taarikakanauji/superstore-sales-analysis/tree/main/Superstore%20Sales%20Analysis.SemanticModel)  
- **Project File:** [Superstore Sales Analysis PBIP](https://github.com/taarikakanauji/superstore-sales-analysis/blob/main/Superstore%20Sales%20Analysis.pbip)  
- **Gitignore:** [.gitignore](https://github.com/taarikakanauji/superstore-sales-analysis/blob/main/.gitignore)  

### **Project README (Setup Guide)**  
[README.md](https://github.com/taarikakanauji/superstore-sales-analysis/blob/main/README.md)  

# Conclusion

This Superstore Sales Dashboard empowers stakeholders to:

- Improve Profitability - Boost profits in underperforming regions, segment, and categories

- Strengthen Customer Engagement - Tailor offers and promotions to underperforming segments

- Optimized Inventory & Sales - Data-driven decisions for better stock management and sales efficiency, Regional analysis supports efficient logistics and stock allocation

- Competitive Advantage - Market analysis and strategic investments to lead competitors. Monitor year-over-year trends to anticipate market shifts.

- Sustainable Growth - Consistent YoY growth, strengthened Furniture category, and long-term profitability, Enhance profit margins through targeted actions


By leveraging these insights, marketing and sales efforts can be strategically directed toward top-performing segments and regions, while underperforming categories can be addressed with data-informed strategies. The ability to reset filters and drill down into detailed metrics ensures an intuitive user experience and supports informed, agile decisions. Ultimately, this dashboard serves as a powerful tool for tracking performance, optimizing sales strategies, and driving the company's growth.


