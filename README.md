A comprehensive Power BI semantic model for analyzing CRM sales pipeline data, built on Google BigQuery data sources.

## 📊 Model Overview

This tabular model demonstrates enterprise-level data modeling with advanced DAX calculations, proper relationships, and business intelligence best practices.

### Tables

#### **Salespipeline** (Fact Table)
Central transaction table tracking all sales opportunities with:
- `opportunity_id` - Unique opportunity identifier
- `sales_agent` - Sales representative handling the opportunity
- `product` - Product being sold
- `account` - Customer account
- `deal_stage` - Current stage (Won/Lost/Prospecting/etc.)
- `engage_date` - Date opportunity was initiated
- `close_date` - Date opportunity closed
- `close_value` - Deal amount ($)

#### **Accounts** (Dimension)
Customer account information:
- `account` - Account name
- `sector` - Industry sector
- `year_established` - Year company was founded
- `revenue` - Annual revenue
- `employees` - Headcount
- `office_location` - Primary office location
- `subsidiary_of` - Parent company relationship

#### **Products** (Dimension)
Product catalog:
- `product` - Product name
- `series` - Product line/series
- `sales_price` - List price

#### **Salesteams** (Dimension)
Sales organization structure:
- `sales_agent` - Agent name
- `manager` - Direct manager
- `regional_office` - Office assignment

#### **Data_Dictionary** (Reference)
Metadata reference table with descriptive data fields.

---

## 📈 Key Measures

### Revenue & Deal Metrics
- **`sales_revenue`** - Total revenue from won deals
- **`Average_Deal_Amount`** - Average deal size for won opportunities
- **`deals_active_customers`** - Count of customers with won deals

### Opportunity Metrics
- **`total_oportunities`** - Total count of all opportunities
- **`won_opportunities`** - Count of deals marked as Won
- **`lost_opportunities`** - Count of deals marked as Lost
- **`closed_opportunities`** - Combined count of Won + Lost deals

### Performance KPIs
- **`Win Rate`** - Percentage of closed deals that were won
- **`SalesCicle`** - Average days from engagement to close (closed deals only)

---

## 🎯 Advanced Features

### Calculated Columns
- **`SalesCicleCC`** - Computed sales cycle using DATEDIFF for all rows

### Linguistic Metadata
- Semantic annotations for natural language queries
- Q&A optimization for business terms
- Auto-generated hierarchies for date dimensions

### Time Intelligence
- Date hierarchies (Year → Quarter → Month → Day)
- Automatic local date tables for engage_date and close_date
- Support for temporal analysis

### Data Quality
- Automatic data type inference
- Format strings for currency and dates
- Data categorization for semantic understanding

## 🚀 Usage in Power BI

### Recommended Visualizations
- **KPI Cards:** Win Rate, Average Deal Amount, Sales Revenue
- **Line Charts:** Revenue trends by month/quarter
- **Funnel Chart:** Deal progression through stages
- **Scatter Plot:** Deal value vs. sales cycle days
- **Table:** Opportunity details with agent/account names

### Typical Analysis Patterns
1. **Sales Performance:** Filter by sales_agent, measure by sales_revenue
2. **Pipeline Health:** Compare won_opportunities vs. lost_opportunities by sector
3. **Cycle Efficiency:** Analyze SalesCicle trends by product or team
4. **Customer Insights:** Revenue by account sector and established year

---

## 📝 Data Lineage

**Data Flow:**
```
Google BigQuery (crmsalespipeline dataset)
    └── Public relations tables:
        ├── accounts
        ├── products
        ├── salespipeline (with transformations)
        ├── salesteams
        └── data_dictionary

Power Transformations:
- Product name standardization (GTXPro → GTX Pro)
- Date formatting for fiscal analysis
- Aggregation calculations for KPIs
```

---

## 🔧 Technical Specifications

### Data Model Configuration
- **Fact Table Grain:** One row per opportunity
- **Time Dimension:** Automatic calendar tables
- **Relationship Type:** One-to-Many (dimensional relationships)
- **Filter Direction:** Single direction (from dimensions to facts)

### DAX Patterns Used
- **CALCULATE** - Context modification for measures
- **DISTINCTCOUNT** - Unique value counting
- **DATEDIFF** - Temporal calculations
- **DIVIDE** - Safe division with blank handling
- **AVERAGEX** - Row-by-row calculations

---

## 💡 Business Insights Enabled

This model supports comprehensive sales analytics:
- **Win/Loss Analysis** - Understand conversion rates by segment
- **Pipeline Forecasting** - Project revenue based on stages
- **Territory Performance** - Compare results across regions
- **Product Analysis** - Revenue and volume by product line
- **Team Efficiency** - Sales cycle and win rate by agent/manager

---

## 📌 Portfolio Highlights

✅ **Professional Data Architecture** - Star schema with proper dimensions  
✅ **Advanced DAX Measures** - Business logic encapsulated in semantic layer  
✅ **Semantic Layer** - Linguistic metadata and Q&A optimization  
✅ **Time Intelligence** - Multi-level date hierarchies  
✅ **Enterprise Standards** - Proper naming, documentation, and organization  
✅ **Real-world Data** - Connected to production BigQuery database  

*This model demonstrates expertise in enterprise data modeling, DAX programming, and business intelligence architecture suitable for Fortune 500 analytics environments.*




[link_to_pbi_dashboard](https://app.powerbi.com/view?r=eyJrIjoiOWVjOWNmMGYtMjdkMC00ZTBmLThhMzgtOGQ5ZWEzYmZjYjNjIiwidCI6Ijk1MzQ3NjQyLTI3ZGYtNGUzMy05ZjRiLTFlMTA2MDRhNjAwNCIsImMiOjR9)
