## Overview
This project supports a job application to the Department of Energy, Mines, Industry Regulation and Safety (DEMIRS) by showcasing advanced data wrangling, risk prioritization, and interactive WHS reporting using the Beta Occupational Hazards Dataset (BOHD) from SafeWorkAustralia. 
It includes:
- **Risk scoring and tiering using a composite hazard index** 
- **Integration of employment size to model WHS impact by scale**
- **SQL-style queries via Python (SQLite) for targeted risk extraction**
-  **A dynamic Power BI dashboard for operational and policy stakeholders**

## Files & Notebooks:
1. `whs_data_pipeline.ipynb`: Main pipeline notebook: ingestion, cleaning, composite risk scoring, employment-weighted WHS impact calculation
2. `meta_data.ipynb`: Metadata exploration notebook: hazard groupings, data dictionaries, and preprocessing logic (Survey questions)
3. `whs.pbix`: Interactive Power BI dashboard showing occupation-level WHS risk insights, trend visualizations, and prioritization flags

## How to Use
1️⃣ **Load and Preprocess the Dataset**  
Start by running the pipeline notebook:
```bash
jupyter notebook whs_data_pipeline.ipynb
```
Key transformations include:  
- **Cleaning occupation and column labels** 
- **Mapping hazard variables to physical and psychosocial categories**
- **Calculating a composite WHS risk score**
- **Integrating workforce size to derive WHS Total Impact**

  
2️⃣ **Query Critical Occupations and extract Key Insights**  
Use SQLite-style queries to extract high-risk occupations by exposure, claim frequency, or total impact.

  
3️⃣ **Launch the Dashboard**  
Open the `whs.pbix` file in Power BI Desktop to interact with:
**Risk rankings by occupation**
**Hazard-specific exposure levels**
**Physical vs Psychosocial exposure**
**WHS Total Impact visualizations**
**Occupation risk matrices and recommendations**

  
4️⃣ **Insights & Decision Support**  
This project was driven by real-world operational questions faced by WorkSafe WA. Each question reflects a critical WHS insight required to guide proactive regulation, and each was answered using SQL-style queries, composite scoring, and visual reporting.
The project answers key WHS questions such as:  
1. Which occupations pose the highest WHS risk in WA?  
Objective: Identify roles with the highest exposure to WHS hazards based on a composite risk score.

2. How does risk change when accounting for workforce size?  
Objective: Measure total workforce impact by multiplying each occupation’s risk by the number of people employed in that occupation.

3. Which sectors should DEMIRS prioritize for inspections or outreach?  
Objective: Pinpoint high-impact occupations across sectors to guide WHS resource allocation.

