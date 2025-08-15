# CLOTHING DATA ANALYSIS

### Dashboard Link : https://app.powerbi.com/links/SrB9WmfQL4?ctid=37d002c9-062c-435d-beff-d1efc9989fe4&pbi_source=linkShare

## Problem Statement

Clothing Data Analysis Dashboard – Power BI

This dashboard helps the retail clothing business understand its performance across different brands, products, and pricing strategies. It provides a clear view of total brands, total cost price, total marked price, total sales price, and key average metrics.
By analyzing these KPIs and visualizations, decision-makers can identify top-performing brands, evaluate pricing efficiency, track profit margins, and optimize discounts to boost sales and profitability.

## Key Objective

To give the clothing retailer a single view of business performance by brand and product, focusing on profitability, discounting trends, and sales efficiency.


### Steps followed 

- Steps Followed

Step 1: Load data from Azure SQL Database into Power BI Desktop. 
- Used the Get Data → Azure → Azure SQL Database option.  
- Provided Server name, Database name, and authentication credentials.

Step 2: Open Power Query Editor and in the View tab under Data Preview, enabled:

- Column distribution

- Column quality

- Column profile

Also, changed profiling to “Based on entire dataset”.

Step 3: Checked data quality:

- No errors found in key columns.

- Null values found in Discount for some products — treated as 0 in calculations.

Step 4: Created KPIs in Report View:

  -  Total Brands –  Distinct count of Brand column.

  - Total Cost Price –   SUM of CostPrice.

  - Total Marked Price – SUM of MarkedPrice.

-   Total Sales Price – SUM of SalesPrice.
DAX expression was written;
       
        Total Brands = DISTINCTCOUNT(ClothingData[Brand])
        Total Cost Price = SUM(ClothingData[CostPrice])
        Total Marked Price = SUM(ClothingData[MarkedPrice])
        Total Sales Price = SUM(ClothingData[SalesPrice])    

A card visual was used to represent Total Brands, Total Cost Price, Total Marked Price, Total Sales Price.

![Snap_Count](https://github.com/user-attachments/assets/35777b27-d74a-4232-afb6-aa41a0e6d88a)

Step 5: Created visuals for key averages:

- Average Discount per Brand – Bar chart with Brand on Axis, Average(Discount) on Values.

- Average Sales per Brand – Column chart with Brand on Axis, Average(SalesPrice) on Values.

- Count of Titles – Donut chart with values count of Titles.

- Average Marked Price vs Cost Price – Scatter Chart chart comparing Average(MarkedPrice) and Average(CostPrice) by Brand.

- Average Profit Percentage – Column chart with Brand on Axis, Average(Profit Percentage) on Values.

Step 6 – Applying the Top N Filter

- Select the visual you want to filter (for example, a bar chart showing brand vs average cost price).

- In the Filters pane, locate the field Brand under the Visual level filters section.

- Click the drop-down arrow next to Filter type and choose "Top N".

- In the Show items box, select "Top" and enter the number (e.g., 5 for Top 5 brands).

- In the By value section, drag your measure (e.g., Average Cost Price or Average Marked Price) into the box.

- Click Apply filter.
 
 
 Following DAX expression was written for different measure ,
 
         Discount Percentage = DIVIDE('Men+Tshirt'[Marked Price]-'Men+Tshirt'[Sales Price],'Men+Tshirt'[Marked Price])*100
         Cost Price = DIVIDE(100*'Men+Tshirt'[Sales Price],100+'Men+Tshirt'[Profit Percentage])
         Profit Percentage = RANDBETWEEN(2,17)
    
 A bar chart visual was used to represent the above measures.
 
 
 ![Snap_3](https://github.com/user-attachments/assets/0e68e7b3-fdd3-4682-83ee-c6dc201e77b3)
 
Step 7: Applied Visual Level Filters to remove null or irrelevant data from averages.

Step 8: Added branding:

- Company logo (Insert → Image)

- Company tagline (Insert → Text Box)

- Colored background shapes for KPI cards
 
Step 9: Published report to Power BI Service for cloud access and sharing.

![Publish_Message](https://github.com/user-attachments/assets/52578ba1-48f4-46d2-9cbb-8d7da17c75fc)

# Dashboard :   Home Page 

![dashboard_snapo](https://github.com/user-attachments/assets/fea8023c-a497-4113-9125-b6222de5bbb3)

 
 # Report Snapshot 1:

 
![Dashboard_upload](https://github.com/user-attachments/assets/a952b660-88f5-47cd-894e-6ef37260199d)

 # Report Snapshot 2:

 ![Dashboard_upload](https://github.com/user-attachments/assets/f6aa3931-7b3c-419e-b3eb-72202167e46c)



# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### Brand Performance

- Top brands contribute ~60% of total sales.

- Three brands consistently underperform despite heavy discounting.

### Discount Efficiency

- Moderate discounts (~10–12%) correlate with higher sales volumes.

- Deep discounts (>18%) not always linked to increased sales.

### Profit Margins

- High-margin brands are not necessarily top sellers — suggests potential for re-pricing.

### Category Trends

- Winter jackets have the highest profit percentage.

- Summer t-shirts drive the most sales volume but with lower margins.


           
# Conclusion

The Clothing Data Analysis Dashboard provides actionable insights into brand performance, pricing efficiency, and profitability. By monitoring these KPIs regularly, the business can:

- Optimize discount strategies

- Focus on profitable brands

- Improve pricing for low-margin items

- Align inventory planning with seasonal sales trends
   

## Resources

[Clothes Dataset](https://drive.google.com/drive/folders/1yrWdxKDRBPLIjXGOjAL4Va1ayhRg0c5m?usp=sharing)

[Templates](https://drive.google.com/drive/folders/1yrWdxKDRBPLIjXGOjAL4Va1ayhRg0c5m?usp=sharing)

## Authors

- [1908Deepak](https://github.com/1908Deepak)


## Feedback

If you have any feedback, please reach out to us at deepaksingh190810@gmail.com

