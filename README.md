Olympics Data Engineering Project (Microsoft Fabric)
📖 Project Overview
This project demonstrates an end-to-end Data Engineering pipeline using Microsoft Fabric. I processed historical Olympics data through the Medallion Architecture (Bronze, Silver, Gold) to create a clean, star-schema-based Power BI dashboard.

🛠️ Challenges & Technical Solutions
1. Data Ingestion Issue (The "Shifting" Problem)
Challenge: The source CSV data had inconsistent formatting (extra spaces, quotes ", and commas ,), which caused columns to shift to the right, leading to corrupted data in the Lakehouse.

Solution: I performed a data format conversion from CSV to TXT (Tab-Separated or Fixed format) before ingestion. This ensured data integrity and fixed the alignment issues.

2. Bronze Layer (Raw to Cleansed)
Process: Used Dataflow Gen2 to load raw data.

Transformation: Performed a Merge between the main athlete events and NOC regions.

Data Cleaning: Handled data type conversions and standardized values to prepare for the Silver layer.

3. Silver Layer (Normalization)
Process: Transformed the "One Big Table" into a normalized structure.

Outcome: Created multiple Dimension Tables (DimAthlete, DimGames, DimMedal, etc.) to reduce redundancy and improve query performance.

4. Gold Layer (The Star Schema)
Process: Built the final Fact Table and linked it with the Dimensions.

Data Modeling: Established relationships (1:N) in the Semantic Model to support advanced Power BI analytics.

📊 Data Insights (Power BI)
Based on the final model, the dataset contains:

Total Athletes: ~135K (Distinct Count)

Total Sports: 66
<img width="1318" height="174" alt="Screenshot 2026-04-27 211221" src="https://github.com/user-attachments/assets/2d2b1402-17cf-4824-8eb7-e320b12a8063" />


Regions Involved: 207

Historical Timeline: 35 Olympic Years
