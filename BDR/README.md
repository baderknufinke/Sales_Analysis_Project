BDR / README.md (copy-paste this)

1. Project Overview

The Olist Sales Analysis Project aims to analyze the sales performance of a Brazilian e-commerce marketplace. This includes customer behavior, order lifecycle, seller performance, product categories, and delivery metrics.

2. Business Objectives (What the company wants to know)
	1.	What are total sales, revenue, and order volumes over time?
	2.	Which product categories drive revenue?
	3.	How long do deliveries take vs. promised delivery dates?
	4.	Which sellers perform best?
	5.	What customer segments have the highest lifetime value?
	6.	Where are delays or refund risks happening in the order flow?

3. KPIs
	•	GMV (gross merchandise volume)
	•	Total Orders
	•	Revenue per Month
	•	Repeat Purchase Rate
	•	Delivery Performance (%)
	•	Average Review Score
	•	Seller Rating & Performance
	•	Category Contribution %

4. Dataset

The dataset consists of 9 CSV files:
	•	olist_orders
	•	order_items
	•	order_payments
	•	customers
	•	sellers
	•	geolocation
	•	reviews
	•	products
	•	product_category_translation

5. Data Architecture (What & Why)

A. Local Stage — PostgreSQL

Why?
	•	Perfect for relational modeling
	•	Ideal for cleaning & staging raw data
	•	You learn pure SQL fundamentals

B. Transformation — dbt

Why?
	•	Builds star schema
	•	Version controlled SQL models
	•	Professional standard in analytics engineering

C. Orchestration — Airflow

Why?
	•	Runs daily jobs
	•	Pull raw data → load into Snowflake → trigger dbt
	•	Production-grade automation

D. Warehouse — Snowflake

Why?
	•	Industry standard cloud warehouse
	•	High scalability
	•	Power BI connects easily

E. Visualisation — Power BI

Why?
	•	Most common BI tool
	•	Perfect for interactive dashboards
	•	Will be used for Sales KPIs

F. Copilot Agent

Why?
	•	Automates insights
	•	Can answer questions using the clean dataset
	•	Production-level AI assistant

6. Pipeline Flow
Raw CSVs → PostgreSQL (staging) → dbt (models) →
Airflow (automation) → Snowflake (warehouse) →
Power BI (dashboards) → Copilot Agent (AI insights)