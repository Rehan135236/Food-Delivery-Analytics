# 🍕 Food Delivery Analytics Platform

## End-to-End Data Engineering Pipeline on Databricks

![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![Delta Lake](https://img.shields.io/badge/Delta_Lake-003B5C?style=for-the-badge&logo=delta&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

---

## 📊 Live Dashboard

**[View Interactive Dashboard](https://dbc-0c83f311-fa23.cloud.databricks.com/dashboardsv3/01f17fa0c9c51e6482c6980068d80ac2/published?o=7474656675120317)**

*Note: Access requires Databricks account with permissions*

---

## 📊 Project Overview

This project demonstrates a **complete production-ready data engineering pipeline** built on Databricks for a food delivery platform (similar to Talabat/Deliveroo). It processes thousands of orders and delivers actionable business insights through a professional dashboard with 30+ visualizations.

### Business Challenge

A food delivery platform needs to understand:
- 📈 **Revenue trends** across cities and cuisines
- 👥 **Customer behavior** and lifetime value
- 🚚 **Driver performance** and operational efficiency
- ⏰ **Order patterns** by time and day
- 💳 **Payment method** preferences
- 🚦 **Traffic impact** on delivery operations

### Solution

Built an end-to-end ETL pipeline using:
- **Medallion Architecture** (Bronze → Silver → Gold)
- **PySpark** for data processing
- **Delta Lake** for reliable storage
- **Databricks Dashboard** for 30+ visualizations

---

## 🏗️ Architecture
┌─────────────────────────────────────────────────────────────────────────────┐
│ DATA PIPELINE ARCHITECTURE │
├─────────────────────────────────────────────────────────────────────────────┤
│ │
│ 📁 BRONZE LAYER → 🔧 SILVER LAYER → 📊 GOLD LAYER │
│ (Raw Data) (Cleaned Data) (Business Metrics) │
│ │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────────────────┐ │
│ │ customers │ │ customers │ │ revenue_by_city │ │
│ │ restaurants │ 🧹 │ restaurants │ 📈 │ revenue_by_cuisine │ │
│ │ drivers │ ────▶ │ drivers │ ────▶ │ daily_revenue │ │
│ │ orders │ │ orders │ │ customer_clv │ │
│ │ order_items │ │ order_items │ │ top_customers │ │
│ │ payments │ │ payments │ │ driver_performance │ │
│ └─────────────┘ └─────────────┘ │ orders_by_hour │ │
│ │ orders_by_day │ │
│ 📥 CSV Files ✨ Cleaned Data │ weekend_analysis │ │
│ (Original Source) (Enriched) │ executive_summary │ │
│ └─────────────────────────┘ │
│ │
│ Data Quality Steps: │
│ ✅ Duplicate Removal ✅ NULL Handling ✅ Data Type Fixing │
│ ✅ Schema Validation ✅ Derived Columns ✅ Aggregations │
│ │
└─────────────────────────────────────────────────────────────────────────────┘


---

## 📈 Dashboard Preview

### Page 1: Executive Overview

**Visualizations:**
- 📈 Revenue Trend (Last 30 Days)
- 🏙️ Revenue by City (Horizontal Bar)
- 🍕 Revenue by Cuisine (Donut Chart)
- 📊 City Performance (Combo Chart)

### Page 2: Customer Analytics

**Visualizations:**
- 🏆 Top Customers by Lifetime Value
- 📍 Customer Distribution by City
- 💰 Customer LTV Distribution
- 📅 Weekend vs Weekday Performance
- 💳 Average Order Value by City
- 🔄 Customer Order Frequency
- 🎯 City Revenue Contribution
- 👥 Customer Segments Analysis
- 📊 Revenue vs Customer Count

### Page 3: Operational Analytics

**Visualizations:**
- 🕐 Orders by Hour (Peak Times)
- 💰 Revenue by Hour
- 📅 Orders by Day of Week
- 🚗 Driver Performance Rankings
- 🏆 Top 5 Drivers
- 📊 Driver Revenue vs Deliveries
- 🚦 Traffic Level Distribution
- 📋 Order Status Distribution
- 💳 Payment Method Distribution
- 📏 Delivery Distance Analysis

---

## 🛠️ Technology Stack

| Category | Technology | Purpose |
|----------|------------|---------|
| **Data Processing** | PySpark, Spark SQL | Data transformations, aggregations |
| **Data Storage** | Delta Lake | Reliable, ACID-compliant storage |
| **Data Lake** | Databricks Volumes | Raw data ingestion |
| **Data Architecture** | Medallion (Bronze/Silver/Gold) | Layered data organization |
| **Visualization** | Databricks Dashboard | 30+ interactive visualizations |
| **Version Control** | GitHub | Code management, portfolio |
| **Languages** | Python, SQL | Development |

---

## 📂 Repository Structure

food-delivery-analytics/
│
├── notebooks/
│ ├── 01_Read_CSV.py # Bronze Layer - Data Ingestion
│ ├── 02_Silver_Layer.py # Silver Layer - Data Cleaning
│ └── 03_Gold_Layer.py # Gold Layer - Business Metrics
│
├── sql/
│ ├── bronze_creation.sql # Bronze table creation
│ ├── silver_transformations.sql # Silver layer transformations
│ ├── gold_views.sql # Gold layer business views
│ └── dashboard_queries.sql # All dashboard SQL queries
│
├── data/
│ ├── gold/
│ │ ├── revenue_by_city.csv
│ │ ├── revenue_by_cuisine.csv
│ │ ├── daily_revenue.csv
│ │ ├── top_customers.csv
│ │ ├── driver_performance.csv
│ │ └── executive_summary.csv
│ └── sample_schema.txt # Schema definitions
│
├── dashboard/
│ ├── dashboard_spec.md # Full dashboard specification
│ └── screenshots/
│ ├── page1_executive.png
│ ├── page2_customer.png
│ └── page3_operational.png
│
├── docs/
│ ├── architecture_diagram.png # Architecture flow diagram
│ ├── data_model.md # Data model documentation
│ └── business_questions.md # Business questions answered
│
├── README.md # This file
├── LICENSE # MIT License
└── requirements.txt # Python dependencies


---

## 🚀 Quick Start Guide

### Prerequisites

- ✅ Databricks Workspace (Community Edition or Professional)
- ✅ Python 3.8+
- ✅ Basic understanding of PySpark

### Clone the Repository

```bash
git clone https://github.com/yourusername/food-delivery-analytics.git
cd food-delivery-analytics
