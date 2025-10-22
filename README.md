# Credit Card Dashboard - Power BI Report

## 📊 Overview

This Power BI dashboard provides comprehensive analytics and insights into credit card transactions and customer behavior. The report analyzes customer demographics, transaction patterns, revenue generation, and card usage across different segments.

## 📁 Data Sources

The dashboard uses two primary data files:

### 1. **cc_add.csv** - Credit Card Transaction Details
Contains 185 transaction records with the following fields:

| Field | Description |
|-------|-------------|
| Client_Num | Unique customer identifier |
| Card_Category | Type of credit card (Blue, Silver, Gold, Platinum) |
| Annual_Fees | Annual fee charged for the card |
| Activation_30_Days | Whether card was activated within 30 days (0/1) |
| Customer_Acq_Cost | Cost to acquire the customer |
| Week_Start_Date | Week start date for the transaction |
| Week_Num | Week number (Week-01 to Week-53) |
| Qtr | Quarter (Q1, Q2, Q3, Q4) |
| current_year | Year of the transaction (2023) |
| Credit_Limit | Credit limit assigned to the customer |
| Total_Revolving_Bal | Total revolving balance |
| Total_Trans_Amt | Total transaction amount |
| Total_Trans_Ct | Total transaction count |
| Avg_Utilization_Ratio | Average credit utilization ratio |
| Use Chip | Transaction method (Chip, Swipe, Online) |
| Exp Type | Expenditure category (Entertainment, Fuel, Travel, Grocery, Food, Bills) |
| Interest_Earned | Interest earned from the customer |
| Delinquent_Acc | Delinquent account indicator (0/1) |

### 2. **cust_add.csv** - Customer Demographics
Contains 185 customer records with the following fields:

| Field | Description |
|-------|-------------|
| Client_Num | Unique customer identifier (links to cc_add.csv) |
| Customer_Age | Age of the customer |
| Gender | Gender (M/F) |
| Dependent_Count | Number of dependents (0-5) |
| Education_Level | Education level (Uneducated, High School, Graduate, Post-Graduate, Doctorate, Unknown) |
| Marital_Status | Marital status (Single, Married, Unknown) |
| state_cd | State code (CA, NY, NJ, TX, FL, NV, MN) |
| Zipcode | ZIP code |
| Car_Owner | Car ownership (yes/no) |
| House_Owner | House ownership (yes/no) |
| Personal_loan | Personal loan status (yes/no) |
| contact | Contact method (cellular, telephone, unknown) |
| Customer_Job | Job category (Govt, Selfemployeed, Blue-collar, Businessman, White-collar, Retirees) |
| Income | Annual income |
| Cust_Satisfaction_Score | Customer satisfaction rating (1-5) |

## 📈 Report Structure

The dashboard consists of **2 main pages** with multiple interactive visualizations:

---

### 🔷 Page 1: CC Transc. (Credit Card Transactions)

This page focuses on **transaction analysis and revenue insights**.

#### Key Metrics (Cards)
- **Total Revenue** - Sum of all revenue generated
- **Total Transaction Count** - Total number of transactions
- **Total Interest Earned** - Interest earned from all customers
- **Total Transaction Amount** - Sum of all transaction amounts

#### Visualizations

1. **Revenue & Transaction Trends (Line & Stacked Column Chart)**
   - Shows quarterly trends of Revenue and Transaction Count
   - Helps identify seasonal patterns and growth trends

2. **Revenue by Expenditure Type (Bar Chart)**
   - Breaks down revenue by expense categories (Entertainment, Fuel, Travel, Grocery, Food, Bills)
   - Identifies which spending categories generate the most revenue

3. **Revenue by Education Level (Bar Chart)**
   - Analyzes revenue generation across different education segments
   - Helps target marketing efforts

4. **Revenue by Customer Job (Bar Chart)**
   - Shows revenue distribution across job categories
   - Identifies high-value customer segments

5. **Revenue by Card Category (Bar Chart)**
   - Compares revenue across different card types (Blue, Silver, Gold, Platinum)
   - Helps evaluate card product performance

6. **Revenue by Use Chip (Bar Chart)**
   - Analyzes revenue by transaction method (Chip, Swipe, Online)
   - Tracks digital vs. physical transaction preferences

7. **Card Category Performance Table**
   - Detailed table showing Revenue, Transaction Amount, and Interest Earned by Card Category
   - Provides granular performance metrics

8. **Customer Distribution (Tree Maps)**
   - **By Quarter** - Customer count distribution across Q1-Q4
   - **By Gender** - Gender-based customer segmentation
   - **By Card Category** - Customer distribution across card types
   - **By Income Group** - Customer segmentation by income brackets

9. **Card Performance Ribbon Chart**
   - Multi-metric comparison of Revenue, Transaction Amount, and Interest Earned
   - Shows relative performance across card categories

10. **Week Filter (Slicer)**
    - Interactive date filter to analyze specific time periods
    - Allows drill-down into weekly performance

---

### 🔶 Page 2: CC Cust. (Credit Card Customer Analytics)

This page focuses on **customer demographics and behavior analysis**.

#### Key Metrics (Cards)
- **Total Customer Satisfaction Score** - Sum of all satisfaction ratings
- **Total Income** - Aggregate customer income
- **Total Customer Age** - Sum of customer ages
- **Total Revenue** - Revenue generated (same as Page 1)

#### Visualizations

1. **Revenue Trends by Gender (Line Chart)**
   - Time-series analysis of revenue by gender
   - Includes date hierarchy (Year > Quarter > Month > Day)
   - Identifies gender-based spending patterns over time

2. **Revenue by Education Level (Bar Chart)**
   - Customer education impact on revenue

3. **Revenue by House Ownership (Bar Chart)**
   - Compares revenue from homeowners vs. non-homeowners

4. **Gender Count by Card Category (Bar Chart)**
   - Distribution of genders across card types

5. **Revenue by Customer Job (Bar Chart)**
   - Job category impact on revenue generation

6. **Revenue by Expenditure Type (Bar Chart)**
   - Spending category analysis (duplicate from Page 1 for consistency)

7. **Revenue by State (Bar Chart)**
   - Geographic revenue distribution
   - Helps identify high-performing regions

8. **Revenue by Dependent Count (Bar Chart)**
   - Analyzes how number of dependents affects spending

9. **Revenue by Gender (Tree Map)**
   - Visual representation of gender-based revenue contribution

10. **Card Category Performance Table**
    - Detailed metrics by card type (same as Page 1)

11. **Transaction Method Distribution (Pie Chart)**
    - Shows proportion of Chip vs. Swipe vs. Online transactions

12. **Customer Segmentation (Tree Maps)**
    - **By Card Category** - Customer distribution
    - **By Gender** - Gender segmentation
    - **By Income Group** - Income bracket distribution
    - **By Quarter** - Quarterly customer count
    - **By Age Group** - Age-based segmentation
    - **By Use Chip** - Transaction method preference

13. **Week Filter (Slicer)**
    - Same as Page 1 for time-based filtering

---

## 🎯 Key Insights & Use Cases

### Business Intelligence Applications

1. **Revenue Optimization**
   - Identify high-revenue customer segments
   - Optimize card offerings based on performance
   - Track revenue trends and seasonality

2. **Customer Segmentation**
   - Analyze demographics (age, gender, education, job)
   - Understand geographic distribution
   - Target marketing campaigns effectively

3. **Product Performance**
   - Compare Blue, Silver, Gold, and Platinum card performance
   - Evaluate transaction methods (Chip vs. Swipe vs. Online)
   - Assess card activation rates

4. **Spending Pattern Analysis**
   - Track expenditure categories (Entertainment, Fuel, Travel, etc.)
   - Identify seasonal spending trends
   - Monitor transaction volumes

5. **Risk Management**
   - Monitor credit utilization ratios
   - Track delinquent accounts
   - Analyze customer acquisition costs vs. revenue

6. **Customer Satisfaction**
   - Correlate satisfaction scores with revenue
   - Identify improvement areas

---

## 🔧 How to Use This Dashboard

### Opening the Report
1. Ensure you have **Microsoft Power BI Desktop** installed
2. Open the file: `PowerBI-CC-Dashboard.pbix`
3. The report will load with data from the two CSV files

### Interacting with the Dashboard

- **Slicers**: Use the week date slicer to filter data for specific time periods
- **Drill-Down**: Click on tree maps and charts to drill into detailed data
- **Cross-Filtering**: Click on any visual element to filter other visuals on the same page
- **Hover**: Hover over data points to see detailed tooltips
- **Export**: Right-click on visuals to export data to Excel

### Refreshing Data

1. If you update the CSV files with new data:
   - Go to **Home > Refresh** in Power BI Desktop
   - The dashboard will reload with updated information

2. To modify data sources:
   - Go to **Home > Transform Data > Data Source Settings**
   - Update file paths as needed

---

## 📊 Calculated Measures

The report includes several calculated measures (derived from the data model):

- **Revenue** - Calculated from transaction amounts and interest
- **AgeGroup** - Categorized age brackets
- **IncomeGroup** - Income range categories

---

## 🔒 Data Relationship

The two tables are related through the **Client_Num** field, creating a one-to-many relationship:
- Each customer (cust_add.csv) can have multiple transactions (cc_add.csv)
- This enables cross-analysis of customer demographics and transaction behavior

---

## 📝 Requirements

- **Software**: Microsoft Power BI Desktop (Latest version recommended)
- **Data Files**: 
  - cc_add.csv
  - cust_add.csv
- **File Size**: ~2.8 MB (.pbix file)

---

## 🚀 Future Enhancements

Potential improvements for this dashboard:

1. Add predictive analytics for revenue forecasting
2. Include customer churn analysis
3. Add geographical maps for state-wise visualization
4. Implement real-time data refresh capabilities
5. Create mobile-optimized views
6. Add KPI indicators with targets vs. actuals
7. Include year-over-year comparison metrics

---

## 📞 Support

For questions or issues with this dashboard:
- Check that all CSV files are in the same directory as the .pbix file
- Ensure Power BI Desktop is up to date
- Verify data file formats match the expected schema

---

## 📄 License

This dashboard is provided as-is for analytical and educational purposes.

---

**Last Updated**: October 2024  
**Data Period**: 2023 (Week 1 - Week 53)  
**Total Records**: 185 customers with 185 transaction records
