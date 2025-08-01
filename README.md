# Customer Churn Analysis Using MySQL

PHPAdmin link: http://localhost/phpmyadmin/index.php?route=/sql&pos=0&db=customer_churnanalysis&table=customers

This project focuses on analyzing customer churn patterns by designing and querying a **relational database** using **MySQL** and **phpMyAdmin**. The goal is to uncover why customers leave, identify at-risk segments, and provide insights to reduce churn and improve retention.

## Project Overview

Churn is a major challenge for many businesses. This project builds a normalized relational database schema to track customer behavior, demographics, and subscription activity. It uses SQL queries to analyze churn trends and generate actionable insights.

## Objectives

- Create a robust relational database to store customer and transaction data.
- Perform SQL-based analysis to understand churn rates and patterns.
- Identify high-risk customer groups using filtering, joins, and aggregations.
- Present data insights that can help drive customer retention strategies.

##  Tools & Technologies

- **MySQL**  
- **phpMyAdmin**  
- **SQL (DDL, DML, Aggregation, Joins)**  
- **ERD Tools** (for visual schema design)

## Database Schema

Includes key tables such as:

- `Customers`: Customer demographic and contact details  
- `Subscriptions`: Subscription plan, status, and dates  
- `Transactions`: Purchase history and engagement  
- `Churn`: Tracks customers who have churned or are at risk  

Relationships:
- One customer can have many subscriptions.
- Churn status is linked back to customers.
- Transactions are tied to subscriptions.

## Sample SQL Queries

```sql
-- Churn rate by subscription plan
SELECT plan_type, 
       COUNT(*) AS total_customers,
       SUM(CASE WHEN churn_status = 'Yes' THEN 1 ELSE 0 END) AS churned,
       ROUND(SUM(CASE WHEN churn_status = 'Yes' THEN 1 ELSE 0 END) / COUNT(*) * 100, 2) AS churn_rate
FROM customers
GROUP BY plan_type;

# Entity Relationship Diagram (ERD)
Visualizes relationships between customer, subscription, churn, and transaction tables.


# How to Use
Launch phpMyAdmin and import the create_tables.sql schema.

Load sample data using insert_sample_data.sql.

Run and customize queries in churn_queries.sql to analyze churn drivers.

# Business Value
- This project helps business stakeholders:

- Understand key drivers of churn

- Predict at-risk customers

- Take data-driven actions to improve customer retention

Author: Precious Benjamin
Role: Data Analyst | SQL Specialist | Business Insights Enthusiast
