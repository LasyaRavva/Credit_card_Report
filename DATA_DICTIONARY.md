# Data Dictionary

## Overview
This document provides detailed definitions for all fields in the Credit Card Dashboard data sources.

---

## cc_add.csv - Credit Card Transaction Details

| Field Name | Data Type | Description | Possible Values / Range | Example |
|------------|-----------|-------------|------------------------|---------|
| Client_Num | Integer | Unique identifier for each customer | 9-digit number | 963607849 |
| Card_Category | String | Type of credit card held by customer | Blue, Silver, Gold, Platinum | Blue |
| Annual_Fees | Decimal | Annual fee charged for the card in dollars | $0 - $500+ | 300 |
| Activation_30_Days | Integer | Indicates if card was activated within 30 days of issuance | 0 (No), 1 (Yes) | 1 |
| Customer_Acq_Cost | Decimal | Cost incurred to acquire the customer in dollars | $40 - $200 | 108 |
| Week_Start_Date | Date | Start date of the week for the transaction | Date format: DD-MM-YYYY | 31-12-2023 |
| Week_Num | String | Week number of the year | Week-01 to Week-53 | Week-53 |
| Qtr | String | Quarter of the year | Q1, Q2, Q3, Q4 | Q4 |
| current_year | Integer | Year of the transaction | 2023 | 2023 |
| Credit_Limit | Decimal | Maximum credit limit assigned to customer in dollars | $1,000 - $30,000+ | 14315 |
| Total_Revolving_Bal | Decimal | Total revolving balance on the card in dollars | $0 - $2,000+ | 690 |
| Total_Trans_Amt | Decimal | Total transaction amount in dollars | $2,000 - $10,000+ | 9603 |
| Total_Trans_Ct | Integer | Total number of transactions | 20 - 90 | 56 |
| Avg_Utilization_Ratio | Decimal | Average credit utilization ratio (balance/limit) | 0.0 - 1.0 (0% - 100%) | 0.048 |
| Use Chip | String | Method used for transactions | Chip, Swipe, Online | Swipe |
| Exp Type | String | Category of expenditure | Entertainment, Fuel, Travel, Grocery, Food, Bills | Entertainment |
| Interest_Earned | Decimal | Interest earned from customer in dollars | $100 - $1,500+ | 598.69 |
| Delinquent_Acc | Integer | Indicates if account is delinquent | 0 (No), 1 (Yes) | 0 |

**Total Records**: 185  
**Primary Key**: Client_Num (for transaction records)

---

## cust_add.csv - Customer Demographics

| Field Name | Data Type | Description | Possible Values / Range | Example |
|------------|-----------|-------------|------------------------|---------|
| Client_Num | Integer | Unique identifier for each customer (links to cc_add.csv) | 9-digit number | 963607849 |
| Customer_Age | Integer | Age of the customer in years | 18 - 80+ | 42 |
| Gender | String | Gender of the customer | M (Male), F (Female) | F |
| Dependent_Count | Integer | Number of dependents | 0 - 5 | 3 |
| Education_Level | String | Highest education level attained | Uneducated, High School, Graduate, Post-Graduate, Doctorate, Unknown | Uneducated |
| Marital_Status | String | Marital status of customer | Single, Married, Unknown | Married |
| state_cd | String | State code (US state abbreviation) | CA, NY, NJ, TX, FL, NV, MN | CA |
| Zipcode | Integer | ZIP code of customer residence | 5-digit ZIP code | 91750 |
| Car_Owner | String | Indicates if customer owns a car | yes, no | no |
| House_Owner | String | Indicates if customer owns a house | yes, no | no |
| Personal_loan | String | Indicates if customer has a personal loan | yes, no | yes |
| contact | String | Preferred contact method | cellular, telephone, unknown | cellular |
| Customer_Job | String | Job category or employment type | Govt, Selfemployeed, Blue-collar, Businessman, White-collar, Retirees | Govt |
| Income | Decimal | Annual income in dollars | $20,000 - $200,000+ | 30574 |
| Cust_Satisfaction_Score | Integer | Customer satisfaction rating | 1 - 5 (1=Very Dissatisfied, 5=Very Satisfied) | 1 |

**Total Records**: 185  
**Primary Key**: Client_Num

---

## Calculated Fields / Measures

The following fields are calculated in the Power BI data model:

### Revenue
- **Type**: Measure
- **Calculation**: Derived from transaction amounts and interest earned
- **Used in**: Multiple visualizations across both pages

### AgeGroup
- **Type**: Calculated Column
- **Purpose**: Groups customers into age brackets for analysis
- **Typical Ranges**: 18-25, 26-35, 36-45, 46-55, 56-65, 65+

### IncomeGroup
- **Type**: Calculated Column
- **Purpose**: Categorizes customers by income level
- **Typical Ranges**: Low (<$30K), Medium ($30K-$60K), High ($60K-$100K), Very High (>$100K)

---

## Data Relationships

### Primary Relationship
- **From**: cc_add.csv (Client_Num)
- **To**: cust_add.csv (Client_Num)
- **Type**: Many-to-One
- **Cardinality**: Many transactions per customer
- **Cross-filter Direction**: Both (allows filtering from either table)

This relationship enables:
- Joining customer demographics with transaction data
- Analyzing revenue by customer attributes
- Segmenting transactions by customer characteristics

---

## Data Quality Notes

### Missing Values
- Some fields may contain "Unknown" values (e.g., Education_Level, Marital_Status)
- Contact method may be "unknown" for some customers
- Zero values in Total_Revolving_Bal indicate no outstanding balance

### Data Integrity
- Client_Num is consistent across both files
- All dates are within 2023
- All transactions have associated customer records

### Constraints
- Customer_Age: Always positive integer
- Cust_Satisfaction_Score: Range 1-5
- Activation_30_Days: Binary (0 or 1)
- Delinquent_Acc: Binary (0 or 1)
- Avg_Utilization_Ratio: Range 0.0-1.0

---

## Field Usage in Dashboard

### Most Frequently Used Fields

**For Segmentation**:
- Card_Category (appears in 8+ visuals)
- Gender (appears in 6+ visuals)
- Education_Level (appears in 4+ visuals)
- Customer_Job (appears in 4+ visuals)

**For Metrics**:
- Revenue (appears in 15+ visuals)
- Total_Trans_Amt (appears in 5+ visuals)
- Interest_Earned (appears in 4+ visuals)
- Total_Trans_Ct (appears in 3+ visuals)

**For Time Analysis**:
- Week_Start_Date (used in slicers and trend charts)
- Qtr (used in quarterly analysis)
- Week_Num (available for weekly trends)

---

## Business Definitions

### Key Terms

**Revenue**: Total monetary value generated from a customer, including transaction amounts and interest earned

**Credit Utilization Ratio**: Percentage of available credit being used (Revolving Balance ÷ Credit Limit)

**Delinquent Account**: Account with overdue payments or payment violations

**Acquisition Cost**: Total marketing and operational cost to acquire a new customer

**Revolving Balance**: Outstanding balance carried over from previous billing cycles

**Transaction Count**: Number of individual transactions made by customer

---

## Data Collection Period

- **Start Date**: January 2023 (Week 1)
- **End Date**: December 2023 (Week 53)
- **Frequency**: Weekly aggregation
- **Coverage**: Full year 2023

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | Nov 2024 | Initial data dictionary created |

---

## Notes for Data Updates

When updating the CSV files:
1. Maintain the same column order and names
2. Ensure Client_Num consistency between files
3. Keep date formats consistent (DD-MM-YYYY)
4. Validate that categorical fields use exact same values
5. Check for null/empty values before refresh
6. Ensure numeric fields are properly formatted

---

For usage instructions, see [README.md](README.md)  
For quick reference, see [QUICK_REFERENCE.md](QUICK_REFERENCE.md)
