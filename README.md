# 🛒 Retail E-Commerce Database & Analytics Workspace

Welcome to the **Retail E-Commerce Database & Analytics Workspace**! This repository features a comprehensive, multi-tier MySQL relational database structure built to model and analyze a realistic retail e-commerce platform. It captures the full transactional lifecycle of an online shop—from the moment a customer signs up to granular order shipping logistics.

The core of this workspace is a progressive **35-question SQL analytical framework** designed to bridge the gap between raw data storage and actionable Business Intelligence (BI) modeling.

---

## 🎯 Project Objectives

* **Relational Data Modeling:** Designs and enforces structural integrity across four closely connected retail tables using primary keys, foreign keys, and specific constraints.
* **Progressive Skill Track:** Provides a structured learning track divided into **3 distinct operational tiers** (Basic, Intermediate, and Advanced Analytics) to master native SQL querying.
* **Data-Driven Operations:** Contains ready-to-run queries to extract vital retail KPIs like Customer Lifetime Value (CLV), platform retention rates, order aging trends, and supply chain dispatch speeds.

---

## 🗺️ Database Architecture & Schema

The platform runs on a robust schema structured around a central transactional nexus. 

### Entity Relationship Structure
* **Customers:** Stores user profiles including unique IDs, names, genders, cities, and sign-up dates.
* **Products:** Tracks inventory item details, categories, and unit retail prices.
* **Orders:** Records transaction specifics like order dates, shipping dates, and fulfillment statuses.
* **Order Details:** Captures granular line-item records including ordered quantities, applied prices, and item discounts.

┌──────────────────────────┐               ┌──────────────────────────┐
│        CUSTOMERS         │               │         PRODUCTS         │
├──────────────────────────┤               ├──────────────────────────┤
│ PK │ custId (INT, AI)    │               │ PK │ prodId (INT, AI)    │
│    │ custName (VARCHAR)  │               │    │ prodName (VARCHAR)  │
│    │ gender (ENUM)       │               │    │ category (VARCHAR)  │
│    │ city (VARCHAR)      │               │    │ unitPrice (DECIMAL) │
└────────────┬─────────────┘               └─────────────┬────────────┘
│ 1                                         │ 1
│                                           │
│ N                                         │ N
┌────────────▼─────────────┐               ┌─────────────▼────────────┐
│          ORDERS          │               │      ORDER DETAILS       │
├──────────────────────────┤               ├──────────────────────────┤
│ PK │ orderId (INT, AI)   │ 1           N │ PK │ detailId (INT, AI)  │
│ FK │ custId (INT) ───────┼───────────────► FK │ orderId (INT)       │
│    │ orderDate (DATE)    │               │ FK │ prodId (INT)        │
│    │ shipDate (DATE)     │               │    │ quantity (INT)      │
│    │ orderStatus (ENUM)  │               │    │ price (DECIMAL)     │
│    └─────────────────────┘               │    │ discount (DECIMAL)  │
└──────────────────────────┘


---

## 📊 Core Business Insights Extracted

1. **Customer Cohorts & Geospatial Clustering:** Grouping users by location (e.g., Mumbai, Delhi, Pune, Bengaluru) to optimize local marketing and grouping buyers into tiered spend profiles (Low, Medium, High).
2. **Financial & Revenue Performance:** Aggregating metrics to pinpoint top-earning categories and calculating historical net **Customer Lifetime Value (CLV)** to identify VIP customers.
3. **Supply Chain & Operational Efficiency:** Tracking order fulfillment delays via live date math and calculating late dispatch rates to manage delivery service level agreements (SLAs).
4. **Advanced Window Functions:** Utilizing tools like `RANK()`, `LEAD()`, and `LAG()` to determine top localized market leaders and isolate seasonal revenue shifts over time.

---

## 🛠️ Query Execution Track Directory

The query workbook is organized progressively by complexity to evaluate your data analytical track:

* **Level 1: Basic Queries (1–10):** Basic table filtering, simple column projections, sorting (`ORDER BY`), and single-table calculations (`COUNT`).
* **Level 2: Intermediate Queries (11–22):** Multi-table join operations (`INNER JOIN`, `LEFT JOIN`), subqueries, conditional logic filters (`HAVING`), and exclusions (`NOT EXISTS`).
* **Level 3: Advanced Analytics (23–35):** Complex analytics structures including window functions (`RANK() OVER`), time-series aging vectors, and automated customer behavioral clustering.

  ## Previews of my Queries

![Retail-Sales-Analysis-Using-SQL](level%20-%201.png)  
