# Methodology

## 1. Data Collection
Source: Inpatient discharge dataset (27K+ rows)

Columns include:
- Demographics (Age Group, Gender, Race)
- Clinical Details (APR-DRG, Severity)
- Operational Metrics (LOS, Discharge Disposition)
- Financials (Total Charges, Total Costs)
- Geographic hierarchy (Health Service Area → County → Facility)

## 2. Data Cleaning (Power Query)
Key steps:
- Removed invalid or missing values in core metrics  
- Standardized facility names  
- Converted data types (LOS as whole number, costs as decimals)
- Extracted hierarchy fields for drilldown:
  - Health Service Area
  - County
  - Facility

## 3. Data Modeling
Model designed using **Star Schema**:
- **Fact Table**: Admissions (LOS, cost, charge, severity)
- **Dimension Tables**:
  - Facilities
  - Demographics
  - Diagnoses
  - Procedure
  - Severity

Relationships:
- One-to-many from dimensions → fact table  
- Slicer hierarchy built using dimension fields  

## 4. Calculation Strategy (DAX)
Key measure groups:
- LOS Benchmarking  
- Cost Benchmarking  
- Efficiency Scores  
- Profitability Metrics  
- Recommendation Logic  

Switch-based logic used for:
- Dynamic recommendation engine  
- Conditional coloring  
- Dynamic titles  

## 5. Visualization Strategy
- Executive KPIs for quick insight  
- Scatter plots for efficiency clusters  
- Gauges for benchmarking  
- Key Influencers & Decomposition Trees for root-cause analysis  
- Hierarchical slicer drives all pages  

## 6. User Experience Enhancements
- Dynamic page titles  
- Hierarchical filters  
- Clean layout with consistent formatting  
- Automated recommendations for decision-makers  
