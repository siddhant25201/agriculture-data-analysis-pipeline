# 📊 Agriculture Data Analysis (AWS S3 + Snowflake + Power BI)

## 🚀 Project Overview
This project demonstrates an end-to-end cloud-based data analytics pipeline using **AWS S3, Snowflake, and Power BI** to analyze agricultural data.

The objective is to transform raw agricultural datasets into meaningful insights by leveraging modern data engineering and visualization tools.

---

## 🏗️ Architecture
AWS S3 (Raw Data Storage)
        ↓
Snowflake (Data Warehousing & Transformation)
        ↓
Power BI (Visualization & Dashboarding)

---

## 🔧 Tech Stack
- **Cloud Storage:** AWS S3
- **Data Warehouse:** Snowflake
- **Data Visualization:** Power BI
- **Query Language:** SQL

---

## 📂 Data Pipeline Workflow

### 1️⃣ Data Ingestion
- Raw dataset stored in **AWS S3 bucket**
- Connected using **Snowflake Storage Integration**
- External stage created to access S3 data

### 2️⃣ Data Loading
- Data loaded into Snowflake using:

```sql
COPY INTO PBI_Dataset 
FROM @pbi_stage
FILE_FORMAT = (TYPE=CSV FIELD_DELIMITER=',' SKIP_HEADER=1)
ON_ERROR = 'CONTINUE';
```

### 3️⃣ Data Transformation
Performed multiple transformations:
- Created derived dataset (`agriculture`)
- Adjusted numerical values:
  - Rainfall increased by **10%**
  - Area reduced by **10%**
- Feature Engineering:
  - **Year Groups:** (Y1, Y2, Y3)
  - **Rainfall Categories:** Low, Medium, High

### 4️⃣ Data Modeling
- Structured dataset for analytics
- Aggregations performed (e.g., yearly counts)

### 5️⃣ Data Visualization
- Interactive dashboard built in **Power BI**
- Connected directly to Snowflake processed data

---

## 📊 Key Insights
- Identified trends in **crop yield vs rainfall categories**
- Segmented data across **time periods (Year Groups)**
- Analyzed impact of:
  - Rainfall
  - Temperature
  - Soil Type
  - Irrigation
- Enabled comparison across multiple agricultural factors

---

## 📈 Dashboard Features
- Year-wise analysis
- Rainfall category segmentation
- Crop and seasonal trends
- Interactive filters and drill-down capabilities

---

## 💡 Key Learnings
- Building scalable **ETL pipelines in cloud**
- Snowflake **data integration with AWS S3**
- Writing optimized SQL transformations
- Designing **business-ready dashboards in Power BI**

---

## 🔮 Future Improvements
- Automate pipeline using **Snowflake Tasks / Streams**
- Add real-time data ingestion
- Integrate ML models for yield prediction

---

## 📌 Conclusion
This project showcases a complete **modern data analytics workflow**, transforming raw cloud data into actionable insights through efficient data engineering and visualization.
