## Overview
This project supports a job application to the Department of Energy, Mines, Industry Regulation and Safety (DEMIRS) by showcasing advanced data wrangling, risk prioritization, and interactive WHS reporting using the Beta Occupational Hazards Dataset (BOHD) from SafeWorkAustralia. 
It includes:
- **Risk scoring and tiering using a composite hazard index** 
- **Integration of employment size to model WHS impact by scale**
- **SQL-style queries via Python (SQLite) for targeted risk extraction**
-  **A dynamic Power BI dashboard for operational and policy stakeholders**

## Files & Notebooks
1. `whs_data_pipeline.ipynb`: Main pipeline notebook: ingestion, cleaning, composite risk scoring, employment-weighted WHS impact calculation
2. `meta_data.ipynb`: Metadata exploration notebook: hazard groupings, data dictionaries, and preprocessing logic (Survey questions)
3. `whs.pbix`: Interactive Power BI dashboard showing occupation-level WHS risk insights, trend visualizations, and prioritization flags

## Data Dictionary   
Detailed descriptions of key fields and metrics:  
**1. Serious Claim Rate** : The number of accepted serious workers’ compensation claims per 1,000 workers in an occupation.  
**2. Composite Risk Score** : A combined metric (scaled 0–1) that aggregates exposure to multiple WHS hazards; both physical (manual handling, cramped posture) and psychosocial (aggression, time pressure).  
**3. Physical Hazard Score** : Average exposure score for physical demands such as force, repetitive movement, loud environments, or contaminants.  
**4. Psychosocial Hazard Score** : Average exposure score to risks like dealing with aggression, emotional labor, and time pressure.  
**5. WHS Total Impact** : Composite Risk Score x Total employment (000s) - estimates workforce-level impact of WHS exposure.  
**6. Risk Tier** : Classification of composite risk score as Low, Medium, or High.  
**7. Impact Tier** : Classification of total impact (population-scale) as Moderate, High, or Critical, used to guide priorities.  

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
- Which occupations pose the highest WHS risk in WA?  
Objective: Identify roles with the highest exposure to WHS hazards based on a composite risk score.

- How does risk change when accounting for workforce size?  
Objective: Measure total workforce impact by multiplying each occupation’s risk by the number of people employed in that occupation.

- Which sectors should DEMIRS prioritize for inspections or outreach?  
Objective: Pinpoint high-impact occupations across sectors to guide WHS resource allocation.

