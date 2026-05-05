# Investment-portfolio-analytics-warehouse
****Project Overview

For a business to flourish, it must effectively manage its capital. In investment management, capital is deployed across multiple asset classes, including equities, fixed income, real estate, and alternative investments.

However, raw data on its own does not provide clarity or direction.

This project builds a SQL based analytics warehouse and Business Intelligence (BI) solution designed to transform fragmented investment data into structured, decision-ready insights for portfolio management and business performance analysis.

It bridges the gap between data storage → analytics → visualization → decision-making.

Project Objectives

This project answers the following core business questions:

Who are the top clients by portfolio size?
Which asset classes generate the highest returns?
What is the risk distribution across portfolios?
How diversified are client investments?
Where is revenue concentrated (client and asset level)?

Tools & Technologies
SQL (PostgreSQL / pgAdmin) → Data modeling, querying, analytics
Data Warehousing Concepts → Schema design (core tables)
Excel / CSV → Data preparation
Business Intelligence → Visuals

****Project Architecture

PHASE 1 — Schema Setup (Warehouse Foundation)
Purpose

To build a structured data environment that supports scalable and reliable analytics.

Design Approach

A multi-schema warehouse architecture was implemented:

staging → raw ingestion layer (future pipeline-ready)
core → cleaned relational tables
analytics → reporting and KPI layer

- Client Table: Represents investors across different regions.
BENEFIT:
-- Improves scalability and mirrors real enterprise data
-- warehouse structure used in financial analytics platforms.
 PURPOSE:
-- Seeds the warehouse with a diversified international
-- investor base to simulate a realistic multi-country
-- investment portfolio dataset.
ROLE IN WAREHOUSE:
-- Acts as a dimension table supporting segmentation analysis
-- by geography, identity, and investor participation trends.
ANALYTICS QUESTIONS SUPPORTED:
-- Which countries contribute the highest investment volume?
-- How many active clients exist in the portfolio?
-- Client distribution across regions?

- Investments (Fact Table): Captures capital allocation per client.
PURPOSE:
-- Stores portfolio investment transactions linked to clients.
-- Acts as the primary fact table supporting portfolio analytics,
-- risk exposure measurement and return performance evaluation.
-- Seeds the investments fact table with diversified
ROLE IN WAREHOUSE:
-- Central fact table connecting client dimension data to
-- asset classification logic for investment portfolio analysis.
ANALYTICS QUESTIONS SUPPORTED:
--  What is total AUM?
-- Which asset classes dominate portfolio allocation?
-- What is the average return per asset category?
-- How is portfolio risk distributed across clients?
-- Which clients hold the largest investment positions?

- Assets (Classification Table): Standardizes asset classes 
 PURPOSE:
-- Standardizes asset types into structured categories
-- for portfolio segmentation and analytics grouping.
 ROLE IN WAREHOUSE:
-- Acts as a reference dimension table that defines:
-- Risk classification rules
-- Investment band ranges
-- Portfolio grouping logic
 ENABLES ANALYTICS:
-- Asset allocation breakdown
-- Risk exposure analysis
-- Portfolio diversification metrics
Calculate: 
- AUM.
-Asset class that dominates. 
- Average return dominance 
- Risk distribution. 
-Top client by portfolio size.

 AUM/ the total market value of the portfolio is 50.5MN which is Σ of Investment Amounts. 

- Portfolio Allocation(Asset Class dominance): 
  . Infrastructure Fund = 43.56% (22mn) 
  . Real Estate Fund = 29.70% (15mn)
  . Equity Fund = 16.83% (8.5mn)
  . MMF = 5.94% (3mn)
  . Gvt Bond = 3.96% (2mn). 

- conclusion:  The portfolio is heavily skewed toward Infrastructure and Real Estate (≈73% combined), meaning moderately exposed to illiquid assets. Meanwhile, Low risk assets (MMF & Bonds = ~10%) are relatively small to mean a moderate to high risk portfolio profile.

- Average Return per Asset Class:
 . Equity Funds (18.20%)
 . Real Estate Fund (12.50%)
 . Infrastructure Fund (11.40%)
 . Government Bonds (7.80%)
 . MMF (6.10%)
The portfolio is well diversified across risk levels higher returns are concentrated in equities, while safer assets (bonds & money market) act as stability buffers. 

-Risk Distribution profile: 
 . Medium Risk (60.4% | 30.5M). 
 . Low Risk (33.66% | 17M). 
 . High Risk (5.94% | 3M)
The portfolio is predominantly allocated to medium-risk assets, suggesting a balanced investment strategy focused on moderate growth with controlled volatility. However, the relatively low allocation to defensive (low-risk) assets indicates limited downside protection in market downturns.

- Client concentration risk: The portfolio shows significant client concentration risk, with the top three clients accounting for approximately 90% of total Assets Under Management. This indicates dependency on a small number of high-value investors and highlights the importance of client retention strategies and diversification of the investor base.

PHASE 2: BUSINESS INTELLIGENCE (BI VISUALIZATION LAYER)
Before building the visuals, the dataset was validated and structured to ensure analytical accuracy and consistency. Relationships were established between core tables to support a reliable analytical model linking:

Clients (client identity and segmentation)
Investments (investment amounts and allocations)
Asset classes (equities, fixed income, real estate, alternatives)
Risk classification (risk levels per investment)

Data integrity checks were performed using SQL queries to:

Validate total investment aggregation across asset classes
Confirm client-level investment consistency
Ensure accurate mapping between clients, assets, and risk categories

1. Stacked Bar Chart: Investment Allocation by Asset Class.
This visualization displays the sum of investment amounts across different asset classes.

It provides a clear breakdown of how capital is distributed across:
Equities
Fixed Income
Real Estate
Alternative Investments

Business Insight:
This chart highlights portfolio diversification levels and reveals which asset classes dominate capital allocation within the investment portfolio.

2. Clustered Bar Chart: Client Investment Contribution.
This visual maps total investment amounts against individual clients (Full Name).

Business Insight:
It enables identification of:
Top contributing clients
Client concentration risk
Revenue dependency on high-value investors

This supports client segmentation and relationship management strategies.

3. Pie Chart: Risk Distribution of Investments
This visualization shows the sum of investment amounts grouped by risk level.

Business Insight:
It provides an overview of:
Low, medium, and high-risk exposure within the portfolio
Overall risk appetite of the client base
Portfolio risk balance and concentration levels

This is key for assessing investment stability and risk management posture.

4. KPI Cards: Assets Under Management (AUM)
This section summarizes total portfolio value using key performance indicators:

Total AUM: Aggregated investment portfolio value
Maximum Investment: 4.3 Billion
Minimum Investment: 252 Million

Business Insight:
These KPIs provide a high-level snapshot of portfolio scale and distribution, highlighting extremes in client investment behavior and overall capital size.


CONCLUSION: 
This project delivers an end-to-end Investment Portfolio solution built using SQL for data analytics and BI for data visualization and insight delivery.
The SQL layer establishes a structured and reliable analytics warehouse by transforming raw investment data into a well-modeled dataset. Through defined relationships, data validation, and aggregation logic.
The BI layer builds on this foundation by converting the structured data into interactive dashboards that provide clear visibility into key investment dimensions, including asset allocation, client contribution, risk distribution, and AUM.
Together, these two tools form a complete analytics pipeline that connects data preparation, modeling, and visualization to business decision-making. The result is a system that enables better understanding of portfolio performance, capital allocation, and risk concentration.

NOTE: This project is intended for learning and practice purposes only.

