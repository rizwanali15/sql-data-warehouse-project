# 📊 Data Warehouse & Analytics Project

This project demonstrates an end-to-end **Data Warehouse and Analytics solution**, covering data ingestion, cleaning, transformation, dimensional modeling, and analytical reporting.

The goal is to build a practical **Modern Data Warehouse** using SQL Server and industry-standard data engineering concepts.

---

## 🏗️ Data Architecture

The project follows the **Medallion Architecture**:

**Bronze → Silver → Gold**

![Data Architecture](docs/data_architecture.png)

### 🥉 Bronze Layer

Stores raw data from **ERP and CRM CSV files** with minimal transformation.

### 🥈 Silver Layer

Cleans, standardizes, transforms, and integrates the source data.

### 🥇 Gold Layer

Contains business-ready data modeled using a **Star Schema** with fact and dimension tables for analytics.

---

## 🔄 ETL Process

```text
ERP CSV Files ──┐
                ├──> Bronze ──> Silver ──> Gold ──> Analytics
CRM CSV Files ──┘
```

The ETL process includes:

* Data ingestion
* Data cleaning and transformation
* Data integration
* Data quality checks
* Loading analytical models

---

## ⭐ Data Modeling

The Gold layer uses a **Star Schema**:

* **Fact Tables** – store measurable business events.
* **Dimension Tables** – provide descriptive information for analysis.

The warehouse focuses on the **latest available dataset**, without historical tracking.

---

## 📊 Analytics & Reporting

SQL-based analysis focuses on:

* 👥 Customer Behavior
* 📦 Product Performance
* 📈 Sales Trends
* 💰 Revenue & Sales Metrics

The analysis provides insights to support **data-driven decision-making**.

---

## 🛠️ Technologies

* **SQL Server**
* **T-SQL**
* **SQL Server Management Studio (SSMS)**
* **Git & GitHub**

### Key Concepts

**Data Warehousing · ETL · Medallion Architecture · Data Cleaning · Data Integration · Star Schema · Data Quality · Analytical SQL**

---

## 📂 Repository Structure

```text
data-warehouse-project/
│
├── datasets/              # ERP & CRM source data
├── docs/                  # Architecture & data model documentation
├── scripts/
│   ├── bronze/            # Raw data ingestion
│   ├── silver/            # Cleaning & transformation
│   └── gold/              # Analytical models
├── tests/                 # Data quality tests
├── README.md
├── LICENSE
└── .gitignore
```

---

## 🧪 Data Quality

Data quality checks are performed during the ETL process, including:

* NULL values
* Duplicate records
* Invalid values
* Data consistency
* Referential integrity

---

## 🎯 Project Goal

To transform raw data from multiple sources into a **reliable, structured, and business-ready Data Warehouse** for analytical reporting and insights.

---

## 👨‍💻 About Me

I am a **Computer Science student** developing my skills in **Data Engineering, Data Analytics, SQL, Python, and Data Warehousing**.

I enjoy building ETL pipelines, designing data models, working with databases, and transforming raw data into meaningful insights.

This project is part of my journey toward becoming a **Data Engineer** and building practical, industry-oriented projects.
