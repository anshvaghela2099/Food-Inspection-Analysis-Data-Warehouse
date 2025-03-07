# **Food Inspection Analysis Data Warehouse**

## **Overview**
This repository contains the **Food Inspection Analysis Data Warehouse (DW) project**, the project focuses on analyzing **food inspection data** from **Chicago and Dallas**.

By implementing a **structured data warehouse solution**, this project enables efficient storage, transformation, and visualization of food inspection data. The solution follows a comprehensive **ETL (Extract, Transform, Load) pipeline**, using **SQL Server, Talend, Power BI, and Tableau** to provide actionable insights into food safety compliance.

---

## **Table of Contents**
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Project Phases](#project-phases)
  - [Part 1: Data Profiling and Staging](#part-1-data-profiling-and-staging)
  - [Part 2: Dimensional Modeling](#part-2-dimensional-modeling)
  - [Part 3: Data Integration and ETL](#part-3-data-integration-and-etl)
  - [Part 4: Business Intelligence Dashboards](#part-4-business-intelligence-dashboards)
- [Reports and Analysis](#reports-and-analysis)
- [Author](#author)

---

## **Project Overview**
This project aims to **analyze food inspection data** and provide insights into safety trends, common violations, and potential risk factors across various food establishments in **Chicago and Dallas**. The project follows a structured **ETL workflow**, extracting raw data, transforming it into a meaningful format, and loading it into a **data warehouse** optimized for business intelligence (BI) reporting.

### **Key Objectives**
- **Standardizing data** from multiple sources (Chicago & Dallas)
- **Building a scalable Data Warehouse** using **Talend & SQL Server**
- **Identifying risk factors** by analyzing violations and inspection failures
- **Providing interactive dashboards** using **Power BI and Tableau**
- **Enabling historical analysis** by tracking trends in food inspections

### **Key Analysis Areas**
- **Inspection outcomes** (Pass, Fail, Conditional Pass)
- **Types of inspections** (Routine, Follow-up, Complaint-based)
- **Risk categorization** (High, Medium, Low)
- **Facility types** (Restaurants, Grocery Stores, Schools, etc.)
- **Common violations** (Health code breaches)
- **Geographical distribution** of violations
- **Trends in compliance over time**

---

## **Data Sources**
The dataset is sourced from publicly available **food inspection records** provided by local **Department of Public Health** agencies.

### **Chicago Food Inspections**
- [Chicago Food Inspection Data](https://data.cityofchicago.org/Health-Human-Services/Food-Inspections/4ijn-s7e5/data_preview)  

### **Dallas Food Inspections**
- [Dallas Restaurant and Food Establishment Inspections](https://www.dallasopendata.com/Services/Restaurant-and-Food-Establishment-Inspections-Octo/dri5-wcct/data_preview)  

---

## **Project Phases**

### **Part 1: Data Profiling and Staging**
1. **Extract Data**
   - Downloaded food inspection data from **Chicago and Dallas Open Data Portals**.
   - Converted data into **TSV format** for consistent processing.

2. **Data Profiling**
   - Used **Ydata Profiling and Alteryx** to analyze missing values, duplicate records, and schema inconsistencies.
   - Identified **multi-valued attributes** (e.g., multiple violations per inspection).
   - Documented **data type conversions** (e.g., converting text-based dates to `DATETIME` format).

3. **Create Staging Tables**
   - Created **staging tables (`stg_*`)** in **SQL Server**.
   - Added **audit columns**:
     - `DI_CreateDate`: Timestamp of row load.
     - `DI_WorkflowFileName`: Name of the Alteryx workflow processing the data.

4. **Deliverables**
   - Screenshots of **Alteryx workflow**.
   - **Runtime details** of ETL job execution.
   - **DDL script for staging tables**.
   - **Data profiling report** documenting:
     - Differences in schema between **Chicago and Dallas datasets**.
     - Strategies for merging the datasets.

---

### **Part 2: Dimensional Modeling**
1. **Design Star Schema**
   - Identified key **facts** and **dimensions**.
   - Created a **dimensional model** optimized for reporting.

2. **Fact and Dimension Tables**
   - **Fact Table:** `fact_inspections`
   - **Dimension Tables:**
     - `dim_facility`
     - `dim_inspection_type`
     - `dim_violation`
     - `dim_location`

     ![image](https://github.com/user-attachments/assets/439a02a3-720e-4303-83f5-4194a75b4f1f)


3. **Deliverables**
   - **ERD Diagram (ER/Studio or Navicat)**
   - **DDL scripts** for database schema.
   - **Screenshots of schema creation in SQL Server**.

---

### **Part 3: Data Integration and ETL**
1. **ETL Process Using Talend**
   - Extracted data from **staging tables (`stg_*`)**.
   - Applied **business rules** and transformations.
   - Loaded into **integration schema (`dim_*, fact_*`)**.

2. **Data Validation**
   - Ensured **row counts** matched between source and destination.
   - Used SQL queries to validate **data consistency and rejection logs**.

3. **Deliverables**
   - **Talend job files**.
   - **Screenshots of ETL process**.
   - **SQL scripts for validation**.
   - **Before-and-after row count comparisons**.

---

### **Part 4: Business Intelligence Dashboards**
1. **Visualization Tools**
   - Created **Power BI** and **Tableau** dashboards.
   - Published to **Power BI Service** and **Tableau Online**.

2. **Key Dashboards**
   - **Inspection Performance Report**
   - **Violation Frequency Dashboard**
   - **Geospatial Analysis**
   - **Trend Analysis**

3. **Deliverables**
   - **Screenshots of dashboards**.
   - **Power BI and Tableau workbooks**.

---

## **Reports and Analysis**
### **Key Insights**
- **High-risk locations** based on violation history.
- **Temporal patterns** in inspection failures.
- **Most common violations** across establishments.
- **Comparison of Chicago vs. Dallas** in food safety compliance.

---

## **Author**
**Ansh Vaghela**
[LinkedIn](https://www.linkedin.com/in/anshv1/)  
