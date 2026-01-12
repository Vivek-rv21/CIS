# CIS
Childcare Insight solution
A Real-World Data Warehouse for Childcare Assistance Programs

[
[
[
[
[

🎯 Project Overview
Childcare Child Healthcare Insights Solution is a Microsoft Fabric-powered analytics platform integrating data from enrollment, providers, outreach, and funding sources. It delivers interactive dashboards for stakeholders to monitor program effectiveness, optimize resources, and improve outcomes for low-income families.
​
Built for real-world scenarios like Children's Health Insurance Program (CHIP), it covers after-school programs, summer camps, and family support services with 178+ metrics across 17 reports.
​
.
🏗️ High-Level Architecture
Data flows through Fabric's medallion layers:

Bronze: Raw ingestion from CSV/Excel/SQL sources via Pipelines to OneLake.
Silver: Cleansing, validation, deduplication using Notebooks/Spark.
Gold: Curated marts for Direct Lake/SQL endpoints.

Power BI consumes gold layer for 4 dashboard pages serving policy makers, admins, finance teams, and outreach groups.
​
Flat Files → Fabric Pipelines → Bronze → Silver → Gold → Power BI Dashboards

📊 Subject Areas & Logical Models
1. Outreach & Engagement
Tracks webinars, trainings, events with KPIs: satisfaction rate, engagements, conversion, YoY trends.
Key Questions: Event effectiveness? Channel performance? Target achievement?

Visuals: KPI cards, trends, income group enrollment, event table.
​

2. Financial & Funding
Monitors budgets, grants, donations, utilization by agency/region.
KPIs: Total budget/expenditure, utilization %, fund balance.

Visuals: Top programs, state-wise table, agency grants.
​

3. Provider Information & Quality
Analyzes capacity, enrollment, TRS ratings, complaints, trainings.
KPIs: Providers count, capacity vs. enrollment, avg. TRS.

Visuals: Capacity heatmap, complaints by region, poverty-complaints matrix.
​

4. Program Enrollment
Covers enrollment, waitlists, compliance, attrition by age/program.
KPIs: Total programs/children, waitlist/attrition rate.

Visuals: Enrollment vs. target, capacity utilization, decomposition tree.

**Prerequisites**:-
Microsoft Fabric workspace
Power BI Desktop
Sample data (CSV/Excel from data/ folder)

**Deployment**
# In Fabric: Create Pipeline → Ingest to Bronze → Transform to Gold
# Publish PBIX to workspace


Data Strategy: Full load to staging, incremental to gold using T-SQL deltas.
​

**🔧 Data Quality & Governance**
Validations: Mandatory fields, ranges, referential integrity, dedup by business keys.
Security: RBAC, PII masking, aggregated reporting.
Refresh: Daily incremental for timeliness.


💼 Business Value
| Outcome                | Impact                                                                                   |
| ---------------------- | ---------------------------------------------------------------------------------------- |
| Program Visibility     | Real-time enrollment/waitlists across regions.Childcare_Insights_Documentation-2.docx​   |
| Funding Optimization   | Track utilization, reallocate under-spent funds.Childcare_Insights_Documentation-2.docx​ |
| Outreach Effectiveness | Refine campaigns for underserved families.Childcare_Insights_Documentation-2.docx​       |
| Capacity Planning      | Identify gaps via utilization trends.Childcare_Insights_Documentation-2.docx​            |


📁 Repository Structure
childcare-insights-solution/
├── fabric-pipelines/     # Ingestion & refresh DAGs
├── notebooks/            # Silver/Gold transformations
├── powerbi/              # PBIX files (4 pages, 17 reports)
├── data/                 # Sample sources (anonymized)
├── docs/                 # Logical models & diagrams[file:1]
└── requirements.txt

**Author**:
      Vivek Vallapure, Azure Data Engineer & Instructor.
​
