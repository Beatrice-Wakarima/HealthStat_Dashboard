HealthStat Hospital Efficiency Dashboard

Healthcare Analytics • Power BI • Operational & Cost Efficiency Analysis

An interactive multi-page Power BI dashboard analyzing efficiency, cost structures, severity mix, and operational performance across New York State hospitals using 27,000+ inpatient discharge records.

This project simulates a real consulting engagement for HealthStat, providing insights and recommendations to optimize patient flow, reduce costs, and improve care quality.

Project Structure
HealthStat-Hospital-Efficiency-Dashboard/
│
├── README.md
│
├── data/
│   ├── raw/
│   └── data_dictionary.xlsx
│
├── dashboard/
│   ├── HealthStat Dashboard.pbix
│   ├── Dashboard_PDF_Export.pdf
│   └── screenshots/
│       ├── executive_overview.png
│       ├── los_comparison.png
│       ├── cost_comparison.png
│       └── hospital_profile.png
│
└── docs/
    ├── project_summary.md
    ├── methodology.md
    ├── recommendations.md
    ├── dax_measures.md
    └── visuals_overview.md


1. Executive Summary

Improving efficiency while maintaining high-quality patient care is an ongoing challenge for healthcare facilities.
This project uses data-driven insights to:

Benchmark hospitals
Analyze Length of Stay (LOS) efficiency
Evaluate cost structures and profitability
Understand severity mix
Provide facility-level recommendations

The final deliverable is a 4-page Power BI dashboard with automated benchmarking and recommendations.

 2. Tools & Technologies
Category	Tools
BI & Visualization	Power BI Desktop, Power Query
Analytics	DAX, Key Influencers (AI), Decomposition Tree (AI)
Data Architecture	Star Schema Model
Documentation	Markdown, PDF

Dataset Size: 27,000+ inpatient discharge records
Columns: Demographics, Severity, APR-DRG, Costs, Charges, LOS, Geography

 3. Dashboard Pages
### Page 1 — Executive Overview

High-level operational and financial performance.

KPIs:

Total Admissions

Avg Length of Stay

Avg Cost per Stay

Avg Charge per Stay

Visuals:

Key Influencers (Admissions)

LOS vs Cost Scatter Plot

Severity Distribution

Discharge Disposition Summary

### Page 2 — Length of Stay (LOS) Comparison

Identifies facilities with strong or weak patient flow management.

Metrics:

Avg LOS

LOS Efficiency Score

LOS Benchmark (All Facilities)

Visuals:

Top & Bottom LOS Table

LOS by Severity

Decomposition Tree (Drivers of LOS)

### Page 3 — Cost Comparison

Evaluates cost structures, profitability, and revenue gaps.

Metrics:

Total Charges

Total Costs

Profit Margin

Cost-to-Charge Ratio

Visuals:

Cost vs Charge Comparison

Cost per Stay by Facility

Key Influencers (Cost)

Cost Decomposition Tree

### Page 4 — Hospital Profile (Drill-Through)

Dynamic, auto-generated insights for a selected facility.

Features:

Dynamic Title (based on slicer)

LOS & Cost Gauges vs System Benchmark

Severity Mix Visual

Diagnosis and Disposition Breakdown

AI-Driven Recommendation Engine:

Hospital Recommendation =
SWITCH(
    TRUE(),
    [Avg LOS] > [Avg LOS (All)], "Reduce LOS by improving discharge planning.",
    [Avg Cost per Stay] > [Avg Cost per Stay (All)], "Optimize cost drivers and resource usage.",
    [% Extreme Severity] > 0.25, "Strengthen critical care capacity.",
    [Avg LOS] <= [Avg LOS (All)] && [Avg Cost per Stay] <= [Avg Cost per Stay (All)],
        "Hospital performing efficiently. Maintain excellence.",
    "Monitor performance trends for improvement opportunities."
)

 4. Key Insights
 1. Process Inefficiencies

LOS varies widely, indicating that some hospitals face workflow bottlenecks.

 2. Cost Drivers

High costs correlate strongly with:

Higher severity

Certain counties

Specific APR-DRG categories

 3. Revenue Structure Issues

Cost-to-Charge ratios show variations that signal inconsistent pricing or billing practices.

 5. Strategic Recommendations
Category	Action
Operational	Improve discharge processes, streamline patient flow
Financial	Investigate outlier costs, review resource usage
Quality	Expand severe-case capacity, improve triage
Technology	Implement predictive LOS models, automate reporting
 6. Technical Highlights

 Advanced DAX for benchmarking and efficiency scoring
 AI visuals to identify statistical drivers (LOS, cost)
 Dynamic drill-through profile page
 Automated recommendations using SWITCH logic
 Hierarchical slicers (Service Area → County → Facility)
 Dynamic titles based on user selection

 7. How to Explore the Project

Download the .pbix file (Power BI Desktop required)

View the exported dashboard PDF

Preview screenshots in the dashboard/screenshots/ folder

Read the documentation in /docs/

 8. Contact

If you'd like to collaborate or discuss analytics projects:

 (Beatrice W.)
 Email: beatiewakarima1@gmail.com
 Portfolio: 
