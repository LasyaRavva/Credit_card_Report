# Quick Reference Guide

## Dashboard Pages at a Glance

### 📄 Page 1: CC Transc. (Transaction Analysis)
**Focus**: Transaction patterns, revenue analysis, and card performance

**Top Metrics**:
- Revenue: Sum of all revenue
- Transaction Count: Total transactions
- Interest Earned: Total interest from customers
- Transaction Amount: Sum of all transaction amounts

**Key Charts**:
- Revenue trends by quarter
- Revenue by spending category (Entertainment, Fuel, Travel, Grocery, Food, Bills)
- Card category performance (Blue, Silver, Gold, Platinum)
- Transaction method breakdown (Chip, Swipe, Online)

---

### 📄 Page 2: CC Cust. (Customer Analysis)
**Focus**: Customer demographics, behavior, and satisfaction

**Top Metrics**:
- Customer Satisfaction Score: Aggregate satisfaction
- Total Income: Customer income sum
- Customer Age: Age demographics
- Revenue: Total revenue (cross-reference)

**Key Charts**:
- Revenue trends by gender over time
- Geographic distribution (state-wise)
- Education and job category analysis
- Home ownership impact on revenue
- Age and income group segmentation

---

## Data Schema Quick Reference

### cc_add.csv (Transaction Data)
```
Client_Num → Card_Category → Revenue Metrics (Annual_Fees, Interest_Earned)
                           → Transaction Metrics (Total_Trans_Amt, Total_Trans_Ct)
                           → Credit Metrics (Credit_Limit, Total_Revolving_Bal)
                           → Time Dimension (Week_Start_Date, Week_Num, Qtr)
                           → Behavior (Use Chip, Exp Type)
```

### cust_add.csv (Customer Data)
```
Client_Num → Demographics (Customer_Age, Gender, Dependent_Count)
          → Education/Job (Education_Level, Customer_Job)
          → Location (state_cd, Zipcode)
          → Assets (Car_Owner, House_Owner, Personal_loan)
          → Metrics (Income, Cust_Satisfaction_Score)
```

---

## Common Analysis Scenarios

### 1. Identify Top Revenue Segments
- **Page**: CC Transc.
- **Visuals**: Revenue by Card Category, Revenue by Customer Job
- **Action**: Look for the longest bars in bar charts

### 2. Understand Spending Patterns
- **Page**: CC Transc.
- **Visuals**: Revenue by Expenditure Type, Revenue & Transaction Trends
- **Action**: Analyze which categories drive revenue

### 3. Analyze Customer Demographics
- **Page**: CC Cust.
- **Visuals**: Tree maps (Gender, Age Group, Income Group)
- **Action**: Use slicers to filter by time period

### 4. Track Performance Over Time
- **Page**: CC Transc. or CC Cust.
- **Visuals**: Line charts, Ribbon chart
- **Action**: Use Week Slicer to focus on specific periods

### 5. Compare Transaction Methods
- **Page**: CC Transc.
- **Visuals**: Revenue by Use Chip, Pie Chart on CC Cust.
- **Action**: Identify digital vs. physical preferences

---

## Filters & Slicers

**Available Filters**:
- **Week Start Date** (on both pages): Filter data by specific weeks or date ranges

**Interactive Filtering**:
- Click any visual element to cross-filter other visuals
- Use Ctrl+Click to select multiple items
- Click on white space to clear filters

---

## Visual Types Used

| Visual Type | Count | Purpose |
|-------------|-------|---------|
| Card (KPI) | 8 | Display key metrics at a glance |
| Bar Chart | 14 | Compare categories |
| Line Chart | 2 | Show trends over time |
| Tree Map | 11 | Visualize hierarchical data and proportions |
| Table | 2 | Show detailed data |
| Pie Chart | 1 | Show composition |
| Ribbon Chart | 1 | Compare multiple metrics across categories |
| Combo Chart | 1 | Dual-axis comparison (Revenue + Count) |
| Slicer | 2 | Interactive filtering |
| Text Box | 2 | Labels and headers |

**Total**: 44 visual elements across 2 pages

---

## Color Coding

The dashboard uses a consistent color theme:
- **Blue tones**: Primary metrics and data points
- **Color gradients**: Differentiate quarters (Q1-Q4)
- **Varied colors**: Distinguish categories in tree maps

---

## Tips for Best Experience

1. **Start with slicers**: Filter by date range first to focus your analysis
2. **Cross-filtering**: Click on segments to see how they affect other visuals
3. **Drill-down**: Some charts support hierarchical drill-down (Year → Quarter → Month)
4. **Tooltips**: Hover over data points for detailed information
5. **Export**: Right-click visuals to export underlying data to Excel

---

## Keyboard Shortcuts (Power BI Desktop)

- `Ctrl + S`: Save report
- `Ctrl + O`: Open report
- `F5`: Refresh data
- `Ctrl + E`: Edit query
- `Ctrl + M`: Manage parameters
- `Alt + F`: File menu
- `Esc`: Exit full screen or clear selections

---

## Troubleshooting

**Issue**: Visuals show no data
- **Solution**: Check if filters/slicers are clearing all data; reset filters

**Issue**: Data doesn't refresh
- **Solution**: Go to Home → Refresh or check data source connections

**Issue**: Performance is slow
- **Solution**: Reduce date range using slicers; close other applications

**Issue**: Cannot open .pbix file
- **Solution**: Ensure Power BI Desktop is installed and up to date

---

## File Information

- **Report File**: PowerBI-CC-Dashboard.pbix (2.8 MB)
- **Data Files**: cc_add.csv (18 KB), cust_add.csv (15 KB)
- **Data Period**: 2023, Weeks 1-53
- **Record Count**: 185 customers, 185 transactions
- **Relationships**: One-to-many (Customer → Transactions via Client_Num)

---

## Related Documentation

For comprehensive information, see [README.md](README.md)
