# Store-Insights 📊

![Project Logo](https://github.com/sateeshVFX/Store-Analysis/blob/main/Retail-Store.jpeg)  <!-- Replace with a relevant image or logo URL -->

## Project Overview 🌟

The **Store-Insights** project aims to create a unified dashboard using two datasets—`Orders.csv` and `Details.csv`—to deliver insightful analysis on market operations. The project evaluates revenue trends, category performance, and customer behavior, enabling data-driven decision-making.

---

### Datasets 📂:
- **[Orders.csv](https://github.com/sateeshVFX/Store-Analysis/blob/main/Orders.csv)**: Contains order-level details including:
  - `Order ID`
  - `Order Date`
  - `Customer Name`
  - `City`
  - `PaymentMode`

- **[Details.csv](https://github.com/sateeshVFX/Store-Analysis/blob/main/Details.csv)**: Contains item-level details including:
  - `Order ID`
  - `Category`
  - `Amount`
  - `Profit`
  - `Quantity`
  - `Sub-Category`

---

## Data Cleaning and Transformation 🛠️

Data cleaning and transformation were crucial in ensuring the integrity of the datasets:

1. **Data Cleaning**:
   - Removed duplicates from Orders and Details.
   - Handled missing data by filling missing numerical values and removing rows with null Order IDs.

2. **Data Standardization**:
   - Standardized date formats and categorical values for consistency.

3. **Data Merging**:
   - Merged the two datasets using SQL JOIN.

4. **New Calculated Fields**:
   - Added profit margin calculations and extracted year and month from Order Date for further analysis.

---

## Data Analysis and Insights 📈

#### Aggregated Metrics Using SQL:
- Total Revenue, Total Profit, and Category Performance were calculated and insights derived, such as:
   - Electronics emerged as the most profitable category.
   - Sales peak during specific holiday seasons.
   - Credit Card and EMI are top payment methods.
   - Highest revenue-generating cities identified were Gudur and Kavali.

---

## SQL Queries 📝

A collection of SQL queries used for analysis:

```sql
1. SELECT `Order ID`, Amount, Profit, PaymentMode FROM Details;

2. SELECT Category, SUM(Amount) AS Total_Sales FROM Details GROUP BY Category;

3. SELECT AVG(Profit) AS Average_Profit FROM Details;

4. SELECT Sub-Category, SUM(Amount) AS Total_Sales FROM Details GROUP BY Sub-Category ORDER BY Total_Sales DESC LIMIT 5;

5. SELECT City, COUNT(`Order ID`) AS Order_Count FROM Orders GROUP BY City;

6. SELECT PaymentMode, COUNT(*) AS Frequency FROM Details GROUP BY PaymentMode ORDER BY Frequency DESC LIMIT 1;

7. SELECT * FROM Details WHERE Profit > Amount * 0.5;

8. SELECT Sub-Category, SUM(Quantity) AS Total_Quantity FROM Details GROUP BY Sub-Category;

9. SELECT * FROM Orders WHERE YEAR(STR_TO_DATE(`Order Date`, '%d-%m-%Y')) = 2018;

10. SELECT o.City, SUM(d.Profit) AS Total_Profit FROM Details d JOIN Orders o ON d.`Order ID` = o.`Order ID` GROUP BY o.City;
```

# Power BI Visualizations 📊

The dashboard includes various visualizations designed to provide insights, such as:

- **Total Sales Trend over time** (Line Chart)
- **Profit Distribution by Category** (Bar Chart)
- **Top 5 Cities by Total Sales** (Column Chart)
- **Payment Mode Distribution** (Pie Chart)
- **Sales by Locality** (Map Visualization)

---

## Sample Dashboard
![Dashboard Image](https://github.com/sateeshVFX/Store-Analysis/blob/main/dashboard.png)  <!-- Replace with a link to your actual dashboard image -->

---

## Dashboard Development 🚀

### Steps Taken:
1. **Importing the Dataset**: Loaded cleaned data into Power BI ensuring data integrity.
2. **DAX Formulas**: Developed Key Performance Indicators (KPIs) such as Total Revenue, Average Profit, and YoY Growth.
3. **Interactive Filters**: Implemented slicers for Category, City, and Order Date.
4. **Final Presentation**: Delivered an interactive dashboard for stakeholders to explore data.

---

Thank you for reviewing this section of the project! Feel free to explore the visuals and the underlying data for deeper insights.
