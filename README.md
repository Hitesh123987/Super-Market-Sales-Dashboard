# Super-Market-Sales-Dashboard
Power BI dashboard for Supermarket Sales analysis featuring interactive slicers, KPIs, customer insights, product performance, branch profits, and cost analysis. Includes visual summaries of sales trends, quantity sold by product lines, payment methods, customer demographics, and gross income by city.

# Objective of Project
The goal of this project is to analyze supermarket sales data and generate meaningful business insights related to product performance, customer behavior, revenue, profit, and operational efficiency.

# Steps Followed
1️⃣ Data Import:  
    Loaded the CSV dataset into Power BI Desktop

2️⃣ Data Cleaning & Quality Check:  
   Using Power Query:
   Enabled Column Quality, Column Distribution, Column Profile
   Switched profiling mode to Entire Dataset       
   Verified: ✅ No missing values ✅ No errors ✅ Proper data types

3️⃣ Data Modeling:   
   Corrected data types (Date, Text, Decimal)
   Created DAX measures to calculate KPIs

4️⃣ Dashboard Design:    
   Applied dark background theme
   Added slicers for Date and Product Line

5️⃣ Publishing:      
   Report published to Power BI Service
   Dashboard screenshot exported and added

# DAX Measures
  1. TOTAL QUANTITY:       
           Total Quantity = SUM('Sales'[Quantity])

  2. AVERAGE QUANTITY:       
            Average Quantity = AVERAGE('Sales'[Quantity])
   
  3. AVERAGE GROSS INCOME:        
            Average Gross Income = AVERAGE('Sales'[gross income])
   
  4. TOTAL COST OF GOOD SOLD:       
            Total COGS = SUM('Sales'[cogs])
   
  5. AVERAGE COST OF GOODS SOLD:        
            Average COGS = AVERAGE('Sales'[cogs])
   
  6. PROFIT:          
            Profit = SUM('Sales'[gross income])

  7. Top Selling Product Line:         
     Top Product Line =
          VAR topItem =
            TOPN(
                  1,
                  SUMMARIZE('Sales', 'Sales'[Product line], "Qty", SUM('Sales'[Quantity])),
                [Qty], DESC
                )
           RETURN
          MAXX(topItem, 'Sales'[Product line])

# VISUALS

  **Card KPIs**:-     Total Quantity, Average COGS, Top Product Line                       
  **Tree Map**:-      Average Quantity by Payment Method             
  **Donut Charts**:-  Gender & Member-wise customer split            
  **Bar Chart**:-     Profit by Branch                               
  **Bar Chart**:-     Cost of Goods Sold by Product Line             
  **Line Chart**:-    Quantity & Gross Income trend over time        
  **Table**:-         Avg & Total quantity per product line          
  **slicer**:-        Date & Product line

# Key Insights

1. Electronic Accessories is the highest selling product line.              
2. Branch C generates the highest profit.        
3. COGS highest for Home & Lifestyle and Sports & Travel.          
4. Customer split is almost equal: Male vs Female.            
5. Payment preference leans toward E-Wallet & Credit Card.            
6. Mandalay shows lower sales – scope for promotional campaigns.              
