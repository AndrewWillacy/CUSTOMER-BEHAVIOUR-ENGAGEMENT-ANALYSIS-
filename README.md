# Customer Behaviour & Marketing Performance Analysis

**Retail Customer Analytics Project | 2025**

> *How can customer demographic and purchasing behaviour data be used to improve marketing effectiveness, optimise product focus, and support commercial decision-making across a global retail business?*

---

## Executive Summary

This project analyses customer demographics, purchasing behaviour, product category performance, and marketing campaign effectiveness for a multinational retail business operating across eight countries.

Using a combination of Excel, SQL, and Tableau, the project investigates how demographic characteristics influence purchasing behaviour, identifies the highest-performing marketing channels, and evaluates product sales performance across geographic regions.

The analysis combines structured data cleaning, exploratory analysis, SQL querying, and dashboard development to transform raw transactional and customer data into actionable business insights.

Key findings revealed that:

* Alcohol and meat products generated the majority of total revenue
* Twitter and Instagram significantly outperformed brochure-based advertising
* Germany produced the highest average customer spend despite Spain generating the highest total revenue
* Customer demographics showed identifiable differences in engagement and purchasing behaviour

The final deliverable included a stakeholder-focused Tableau dashboard designed to support operational and marketing decision-making.

---

## Business Problem

A multinational retail business wanted to better understand its customers, purchasing behaviour, and marketing effectiveness in order to support data-driven commercial decision-making.

The primary objectives of the analysis were to:

* Identify core customer demographics
* Understand purchasing behaviour across customer groups
* Evaluate which marketing channels generated the strongest engagement
* Determine which product categories generated the highest revenue
* Explore geographic differences in customer behaviour and sales performance
* Provide actionable recommendations to improve marketing efficiency and commercial performance

The project was designed to support stakeholders responsible for:

* Marketing strategy
* Product performance
* Customer engagement
* Commercial planning
* Operational decision-making

---

## Data Sources

| Source                           | File | Data Collected                                                                                 | Purpose                                      |
| -------------------------------- | ---- | ---------------------------------------------------------------------------------------------- | -------------------------------------------- |
| **Customer Marketing Dataset**   | marketing_data.csv | Customer demographics, purchasing activity by product category, income, household composition (No. of children etc), transaction history, campaign response | Customer behaviour and segmentation analysis |
| **Advertising Campaign Dataset** | ad_data.csv |  Advertising channel exposure per customer (Bulkmail, Twitter, Instagram, Facebook, Brochure), Campaign engagement and advertising channel performance | Marketing effectiveness analysis             |

Two datasets were joined on customer ID using SQL to enable cross-analysis of demographics, purchasing behaviour, and advertising exposure.

The combined datasets included:

* Customer demographic information
* Product category spending
* Income and household data
* Campaign interaction metrics
* Geographic sales information
* Customer engagement behaviour

---

## Tools & Skills Used

| Category                        | Tools / Methods                                                                    |
| ------------------------------- | ---------------------------------------------------------------------------------- |
| **Data Cleaning & EDA**         | Excel (advanced functions, pivot tables, calculated columns)                       |
| **Database & Querying**         | PostgreSQL (table creation, INNER JOIN, CASE, GREATEST/LEAST, aggregate functions) |
| **Data Visualisation**          | Tableau Tableau (interactive dashboard, filters, multiple chart types              |
| **Analysis Techniques**         | Exploratory Data Analysis (EDA), segmentation analysis, trend analysis             |
| **Reporting**                   | Dashboard development, stakeholder reporting                                       |

**Skills demonstrated:**

End-to-end data workflow · Data cleaning and validation · Exploratory analysis (EDA) · SQL database building & querying · Outlier detection and handling · Dashboard development · Business insight generation · Stakeholder-focused reporting · Data visualisation · Commercial analysis


---

## Analytical Approach

The project followed a structured multi-stage workflow combining data cleaning, exploratory analysis, SQL analysis, and dashboard development.

### 1. Data Cleaning & Validation

The raw CSV datasets were initially imported into Excel for cleaning and preparation.

Key cleaning and validation steps included:

* Standardised date formatting
* Removal of duplicate records
* Validation of primary key uniqueness
* Standardisation of text formatting and category labels
* Identification and removal of implausible age records
* Handling of inconsistent marital status categories
* Removal of formatting inconsistencies in income data
* Validation of missing values and data types
* Creation of derived analytical fields including:

  * Customer age
  * Total customer spend

Several data quality issues were identified during preparation:

| Issue Identified                                        | Resolution                             |
| ------------------------------------------------------- | -------------------------------------- |
| Implausible customer ages (>124 years old)              | Removed from analysis                  |
| Duplicate customer records                              | Removed after validation               |
| Inconsistent category labels (e.g. “Single” vs “Alone”) | Standardised                           |
| Extreme income outlier ($666,666)                       | Excluded from income-specific analysis |
| Formatting inconsistencies in income fields             | Cleaned and standardised               |

The cleaning process improved dataset consistency and ensured analytical outputs were reliable and suitable for business reporting.

---

### 2. Exploratory Data Analysis

Exploratory analysis was conducted in Excel to identify demographic, behavioural, and commercial patterns.

The analysis investigated:

* Customer age distribution
* Geographic customer distribution
* Average spend by country
* Income distribution
* Product category sales
* Marketing campaign effectiveness
* Relationships between income and purchasing behaviour

Key exploratory findings included:

* Customer ages ranged from 28 to 84, with an average age of 55
* Married and partnered customers represented the largest customer segment
* Spain generated the highest total revenue due to the size of its customer base
* Germany generated the highest average spend per customer
* Most customers fell within a moderate income range between approximately $20K and $100K

Visualisations created during exploratory analysis included:

* Scatter plots
* Bar charts
* Geographic mapping
* Income distribution analysis
* Product category comparisons

---

### 3. SQL Analysis

Following cleaning and exploratory analysis, the datasets were imported into PostgreSQL for deeper analytical querying.

The SQL analysis focused on:

* Product category performance
* Campaign effectiveness
* Geographic sales analysis
* Customer segmentation
* Revenue comparisons
* Behavioural trends across demographic groups

The database structure included:

* Customer marketing data tables
* Advertising campaign data tables
* Derived calculated fields for analytical reporting

Key SQL findings included:

#### Product Performance

* Alcohol products accounted for approximately 50% of total product sales
* Meat products represented the second-highest revenue category
* Vegetables and chocolate generated the lowest sales performance
* Product preference patterns remained relatively consistent across customer demographics

#### Campaign Effectiveness

* Twitter was identified as the highest-performing advertising channel
* Instagram and Facebook also demonstrated strong engagement performance
* Brochure advertising consistently underperformed across most demographic groups
* Bulk email campaigns showed stronger performance amongst single customers than expected

#### Geographic Performance

* Spain generated significantly higher total revenue than other regions
* Germany produced the highest average customer spend
* Montenegro significantly underperformed relative to all other markets

---

### 4. Dashboard Design & Development

A stakeholder-focused Tableau dashboard was developed to communicate insights clearly and support business decision-making.

The dashboard design prioritised:

* Simplicity and readability
* Clear visual hierarchy
* Accessibility
* Geographic comparison
* Executive-level usability
* Interactive filtering and exploration

Dashboard features included:

| Dashboard Component                     | Purpose                            |
| --------------------------------------- | ---------------------------------- |
| Customer demographic analysis           | Identify core customer groups      |
| Geographic sales mapping                | Compare country-level performance  |
| Product category visualisations         | Highlight key revenue drivers      |
| Marketing campaign performance analysis | Evaluate advertising effectiveness |
| Income and spending comparisons         | Explore customer value patterns    |

The dashboard was designed using a consistent colour scheme and structured layout to support non-technical stakeholders in interpreting insights quickly and effectively.

---

## Key Findings & Business Recommendations

### Finding 1: Product Sales Were Highly Concentrated

Alcohol products represented approximately half of all product sales, with meat products generating the second-highest revenue contribution.

| Product Category Insight                        | Business Impact                    |
| ----------------------------------------------- | ---------------------------------- |
| Alcohol dominated sales performance             | Core commercial revenue driver     |
| Meat products showed consistently strong demand | High-value supporting category     |
| Vegetables and chocolate underperformed         | Potential optimisation opportunity |

#### Recommendation

Prioritise inventory, promotions, and marketing activity around high-performing product categories while reviewing the commercial viability of underperforming categories.

---

### Finding 2: Social Media Significantly Outperformed Traditional Advertising

Twitter, Instagram, and Facebook consistently generated stronger campaign engagement than brochure-based advertising.

| Advertising Channel  | Relative Performance           |
| -------------------- | ------------------------------ |
| Twitter              | Highest-performing             |
| Instagram            | Strong                         |
| Facebook             | Strong                         |
| Bulk Email           | Effective for single customers |
| Brochure Advertising | Weakest-performing             |

#### Recommendation

Increase focus on digital and social media marketing while reducing reliance on lower-performing brochure campaigns.

---

### Finding 3: Geographic Performance Varied Significantly

Although Spain generated the highest total revenue, Germany produced the highest average spend per customer.

| Country Insight                         | Commercial Interpretation |
| --------------------------------------- | ------------------------- |
| Spain generated highest total revenue   | Largest customer base     |
| Germany generated highest average spend | Higher customer value     |
| Montenegro significantly underperformed | Low commercial return     |

#### Recommendation

Develop market-specific strategies focused on:

* Customer growth in high-volume regions
* Customer value optimisation in high-spend regions
* Commercial review of underperforming markets

---

### Finding 4: Demographic Patterns Influenced Engagement Behaviour

Customer demographics demonstrated measurable differences in purchasing and campaign engagement behaviour.

Key observations included:

* Married and partnered customers formed the largest customer group
* Most customers were educated to graduate level or above
* Bulk email campaigns performed particularly well amongst single customers

#### Recommendation

Use demographic segmentation to support more targeted and personalised marketing strategies.

---

## Limitations

Several limitations were identified during the analysis:

* Income data appeared inconsistently recorded in some cases
* Some demographic categories required manual standardisation
* The dataset represented historical behaviour only and could not fully predict future trends
* Several low-volume geographic markets limited comparative analysis reliability
* Customer lifetime value and retention metrics were unavailable

Despite these limitations, the dataset was sufficiently robust to identify clear behavioural and commercial trends.

---

## Future Steps

Potential future enhancements include:

* Customer segmentation modelling using clustering techniques
* Predictive modelling for campaign response behaviour
* Customer lifetime value (CLV) analysis
* Automated ETL pipeline development
* Forecasting product demand by region
* Development of real-time dashboards in Power BI or Tableau
* Integration of transactional and loyalty programme data
* A/B testing framework for campaign optimisation

---

## Dashboard & Deliverables

The project deliverables included:

| Deliverable       | Description                                         |
| ----------------- | --------------------------------------------------- |
| Tableau Dashboard | Interactive stakeholder reporting dashboard         |
| SQL Scripts       | PostgreSQL database creation and analytical queries |
| Technical Report  | Structured business analysis and recommendations    |
| Presentation      | Stakeholder-focused presentation of findings        |

---

## About

This project was completed as part of the **LSE Data Analytics Career Accelerator (2025, Distinction)**.

The analysis focused on transforming raw customer and marketing data into actionable business insights through structured cleaning, exploratory analysis, SQL querying, and dashboard development.

**Andrew Willacy**
[LinkedIn](https://www.linkedin.com/in/andrew-willacy-572682347/) | [GitHub Portfolio](https://github.com/AndrewWillacy) | [andrew.willacy.data@gmail.com](mailto:andrew.willacy.data@gmail.com)



---


# Customer Demographics & Marketing Channel Effectiveness Analysis
**LSE Data Analytics Career Accelerator — DA201 | June 2025**

> *Which customers does this retailer serve, which advertising channels drive the most value, and do demographics influence what people buy?*

---

## Executive Summary

This project analyses customer purchasing behaviour and advertising effectiveness for a global supermarket operating across eight countries. Using Excel, SQL, and Tableau, the analysis identifies clear demographic patterns in the customer base, pinpoints which advertising channels drive the highest average spend, and determines whether product preferences vary by demographic group.

**Key results:** Alcohol accounts for 50% of all product sales regardless of country, marital status, or household composition. Instagram and Facebook drive the highest average customer spend among those exposed to advertising. Brochure advertising is consistently the least effective channel across all segments. Spain dominates revenue by volume but Germany and South Africa produce higher average spend per customer.

---

## Business Problem

A global supermarket operating in eight countries wanted to better understand its customer base to inform marketing strategy and resource allocation. Three core business questions drove the analysis:

> **1. What are the demographics of our customers?**
> **2. Which advertising channels are most effective?**
> **3. Which products sell best, and does that vary by customer demographic?**

The answers were intended to support executive decision-making on advertising spend, market prioritisation, and product focus.

---

## Data Sources

| File | Contents |
|------|----------|
| `marketing_data.csv` | Customer demographics, purchase history by product category, recency, campaign response |
| `ad_data.csv` | Advertising channel exposure per customer (Bulkmail, Twitter, Instagram, Facebook, Brochure) |

Two datasets were joined on customer ID using SQL to enable cross-analysis of demographics, purchasing behaviour, and advertising exposure.

---

## Tools & Skills Used

| Category | Tools |
|----------|-------|
| **Data Cleaning & EDA** | Excel (advanced functions, pivot tables, calculated columns) |
| **Database & Querying** | PostgreSQL (table creation, INNER JOIN, CASE, GREATEST/LEAST, aggregate functions) |
| **Visualisation & Dashboard** | Tableau (interactive dashboard, filters, multiple chart types) |
| **Framework** | IDEAL Problem-Solving Framework (Bransford & Stein, 1984) |

**Skills demonstrated:** End-to-end data workflow · Data cleaning and validation · SQL database design · Multi-table querying · Outlier detection and handling · Dashboard design · Stakeholder-focused insight communication

---

## Analytical Approach

### 1. Data Cleaning (Excel)

The raw dataset required significant preparation before analysis could begin:

- **Date formatting** standardised to DD/MM/YYYY
- **Duplicate detection** — primary key (ID) checked for uniqueness; rows with identical entities across all fields except PK removed as implausible duplicates
- **Outlier removal** — three records showing customer ages over 124 removed as implausible; one income outlier of $666,666 (far above the next highest value) excluded from income-based analysis
- **Standardisation** — marital status categories consolidated: 'Single' and 'Alone' merged; 'YOLO' and 'Absurd' removed (three records, negligible impact)
- **Calculated columns added** — `Age` (derived from Year_Birth) and `Total_Spend` (sum of all product categories per customer)
- **Column renaming** — product category codes translated to meaningful labels (e.g. 'AmtLiq' → 'Alcohol')
- **Data type validation** — Excel TYPE function used to ensure consistent data types throughout

**Key observation:** The youngest customer in the cleaned dataset would have been 15 at the time of registration — flagged as a data quality concern worth investigating further.

### 2. SQL Analysis (PostgreSQL)

A PostgreSQL database was created with two tables — `Marketing_Data` and `ad_data` — with customer ID as the primary key and join field.

Queries addressed each of the three business questions:

**Revenue and product analysis:**
- Total spend aggregated by country using `SUM` and `GROUP BY`
- Most and least popular product categories identified per country and marital status using `GREATEST` and `LEAST` functions within `CASE` statements
- Product preferences cross-referenced by household composition (kids/teens at home vs not)

**Advertising effectiveness:**
- Boolean ad exposure fields cast to integer to enable summation
- Most and least effective channels identified per country and marital status
- A `Media` column was engineered in `ad_data` to enable average spend analysis by channel — customers joined to their advertising exposure and average spend calculated per channel using `ROUND(AVG())` and `ORDER BY Avg_Spend DESC`

**Key SQL technique:** Boolean-to-integer casting (`::INT`) to aggregate advertising exposure data, and `GREATEST`/`LEAST` functions to identify highest and lowest values across multiple product or channel columns within a single query.

### 3. Dashboard Design (Tableau)

The Tableau dashboard was designed with a non-technical executive audience in mind, using a calm blue colour scheme chosen for readability and professionalism. Prototype layouts were planned on paper before build.

**Dashboard components:**
- Age range distribution of customers
- Marital status breakdown
- Education level distribution
- World map showing geographical customer distribution and density
- Income distribution by customer count
- Total sales by product category
- Advertising campaign effectiveness by channel and country

Design decisions prioritised clarity over complexity — filters allow stakeholder exploration without requiring analytical knowledge. Chart types were chosen to match the nature of each variable (bar charts for categories, scatter plots for continuous relationships, maps for geographic data).

---

## Key Findings

### Customer Demographics
The customer base spans 8 countries with ages ranging from 28 to 84 (average 55). The majority are married or in relationships, and most are educated to graduate level or above. Spain has by far the largest customer base (994 customers) and highest total revenue ($652,074), but Germany produces the highest average spend per customer ($694.50), followed closely by the USA ($689.07).

### Product Sales

| Product | Performance |
|---------|-------------|
| Alcohol | 50% of all sales — most popular in every country and across all marital statuses |
| Meat | Second highest overall |
| Vegetables | Consistently worst performing across all segments |

Product preferences do **not** meaningfully vary by marital status, country, or whether children or teenagers are present in the household. Alcohol dominates universally.

### Advertising Effectiveness

| Channel | Avg Spend | Notes |
|---------|-----------|-------|
| Instagram | $1,609 | Highest average spend; highest income customers |
| Facebook | $1,541 | Second highest |
| Brochure | $1,370 | Third — but least effective by country/marital analysis |
| Twitter | $848 | Lower average spend |
| None (no ad exposure) | $532 | Baseline |

Brochure advertising is the least effective channel across nearly every country and marital status segment — the only exception being Montenegro (two customers, statistically negligible).

Bulk email performs surprisingly well among single customers, approaching Twitter effectiveness for that demographic.

---

## Business Recommendations

- **Prioritise Instagram and Facebook** for advertising investment — both drive the highest average customer spend
- **Discontinue or significantly reduce brochure advertising** — consistently least effective across all segments
- **Target single customers with bulk email** — disproportionately effective for this demographic
- **Focus on alcohol and meat** as core product categories; deprioritise vegetable promotions
- **Investigate Germany** — smaller customer base but highest average spend per customer suggests high-value segment worth developing
- **Review Montenegro** — two customers and negligible revenue; assess whether to maintain or exit this market

---

## Limitations

- **Small advertising sample:** Only 292 customers were exposed to at least one advertising channel, limiting the statistical robustness of channel effectiveness conclusions
- **Single ad exposure assumed:** The methodology assigns one channel per customer based on the last Boolean flag set — customers exposed to multiple channels are not fully accounted for
- **Income data inconsistency:** Income values appear to be a mix of annual and monthly figures; no normalisation was possible without additional context
- **15-year-old customer:** The youngest customer would have been 15 at registration — raises data collection questions that could not be resolved with available information
- **Spending score unknown:** No metadata explaining how `Count_success` was calculated — limits interpretation of campaign success metrics
- **Cross-sectional snapshot:** No time dimension in the data; trends over time cannot be assessed

---

## Further Analysis

- **Longitudinal analysis** — track how customer demographics and purchasing behaviour shift over time
- **Multi-channel exposure** — properly account for customers exposed to more than one advertising channel to understand combined channel effects
- **Country-level deep dive** — explore why Germany produces higher average spend despite a smaller customer base
- **Age-segmented advertising analysis** — test whether younger and older customer segments respond differently to specific channels
- **Income normalisation** — clarify whether income figures are annual or monthly and normalise accordingly before including income in regression or clustering analysis

---

## Repository Structure

```
├── data/
│   ├── marketing_data_clean.csv       # Cleaned marketing dataset
│   └── ad_data_clean.csv              # Cleaned advertising dataset
├── sql/
│   └── 2market_queries.sql            # All SQL queries with inline comments
├── tableau/
│   └── dashboard.twbx                 # Tableau packaged workbook
├── report/
│   └── Willacy_Andrew_DA201_Report.pdf
└── README.md
```

---

## Results Summary

| Question | Answer |
|----------|--------|
| Who are the customers? | Primarily aged 28–84 (avg 55), married/together, graduate-educated, concentrated in Spain |
| Which ad channel is most effective? | Instagram (highest avg spend $1,609); Brochure consistently least effective |
| Which products sell best? | Alcohol (50% of all sales) universally; no meaningful demographic variation |

---

## About

This project was completed as part of the **LSE Data Analytics Career Accelerator (DA201: Exploratory Analysis and Presenting Insights), June 2025**, achieving a score of 80%.

**Andrew Willacy**
[LinkedIn](https://www.linkedin.com/in/andrew-willacy-572682347/) | [GitHub Portfolio](https://github.com/AndrewWillacy) | andrew.willacy.data@gmail.com







---


















# CUSTOMER BEHAVIOUR & ENGAGEMENT ANALYSIS
May 2025

Grade: Distinction

Tools used: Excel, SQL (Postgres), Tableau

# Context/Business Questions

Retail sales analysis using Tableau dashboards and business intelligence reporting
Date: June 2025
Tools Used: Excel, SQL (PostgreSQL), Tableau, PowerPoint

2Market is a (fictional) global supermarket chain operating in eight countries with both physical and online storefronts.
The purpose of this analytics project is to help the business understand:

- Who are their customers (demographics: age, marital status etc)

- Which product categories generate the most revenue

- How demographics influence purchasing patterns

- Which advertising channels are most effective

- How customer behaviour varies by geography

Figure 1: The number of customers by country

<img width="750" height="450" alt="Screenshot 2025-12-13 134910" src="https://github.com/user-attachments/assets/e5d1c800-453f-48d9-80ae-5ae6a2a84731" />


# Data Cleaning & Preparation (Excel)

The raw CSV was imported into Excel and cleaned extensively:

- Standardised formatting, removed duplicates and inconsistencies

- Created calculated fields such as Age and Total_Spend

- Cleaned date formats, removed invalid ages (124+ years)

- Resolved inconsistent/erroneous labels in Marital_Status

- Identified income outliers and adjusted analysis accordingly

- Updated product category names for clarity

- Imported cleaned data into PostgreSQL for analysis

# Database Structure

The project uses two PostgreSQL tables:

Marketing_Data

Includes demographics, purchase details, and customer behaviour metrics such as:
Age, Income, Total_Spend, Education, Marital_Status, Country, Kids/Teens, product category spend, and more.

Figure 2: Marketing_Data Table
<img width="900" height="600" alt="Screenshot 2025-12-13 151717" src="https://github.com/user-attachments/assets/fc31ca9c-3dba-44e6-b499-d2c689e799ee" />

ad_data

Contains binary indicators showing whether a customer was exposed to each advertising channel:
Twitter, Instagram, Bulkmail, Facebook, Brochure

Figure 3: Ad_Data Table
<img width="900" height="300" alt="Screenshot 2025-12-13 151842" src="https://github.com/user-attachments/assets/0484f707-b2a5-4054-aeab-749ae308e73e" />


# Analytical Approach (SQL)

SQL was used to:

- Calculate revenue by country

- Identify top product categories globally and by country

- Analyse purchasing behaviour across demographics

- Evaluate which advertising methods drive the most successful customer responses

- Combine exposure + conversion metrics to determine channel effectiveness

- Segment customers by marital status and presence of children/teens

- Assign customers a simplified Media label for deeper spend comparisons

Example SQL tasks included:

Use of GREATEST() and LEAST() to identify best/worst performing product categories and ad channels

Multi-table joins using (INNER JOIN) to combine demographic and advertising data

GROUPBY to group results such as by marital status or country 

CASE logic for categorising customers

Aggregations to compute spend patterns, averages, and customer counts

# Tableau Dashboard

The Tableau dashboard (included as .twbx) includes:

- Customer age distribution

- Marital status & education breakdowns

- Income distributions

- Geographic map of customer locations & density

- Revenue and product category performance

- Advertising channel effectiveness summaries

Figure 4: Tableau Dashboard
<img width="900" height="600" alt="Screenshot 2025-12-13 153958" src="https://github.com/user-attachments/assets/685b0d12-1b62-406f-95fd-34674e667c78" />

The design uses a calm blue palette with clear typography to support executive-level presentations.

# Key Insights
### Customer Demographics

Customer ages range from 28 to 84, average age 55

Majority are married or living with a partner

Most customers have a graduate-level education or higher

Figure 5: Incoome by total spend

<img width="650" height="420" alt="Screenshot 2025-12-13 135615" src="https://github.com/user-attachments/assets/45a9f51f-8882-4c0b-ad4d-1ec35ef3f1a8" />


### Product Sales

Alcohol is the top-selling category, accounting for 50% of sales

Followed by meat, fish, and commodities

Vegetables and chocolate are the lowest performers

This trend is consistent across most countries

### Geographic Insights

Spain: largest customer base and highest revenue

Germany: highest average spend per customer

Montenegro: extremely low customer count → potential market concern

Figure 6: Average customer spend by country

<img width="650" height="400" alt="Screenshot 2025-12-13 135503" src="https://github.com/user-attachments/assets/b6d44b4d-d328-478a-939d-2bfd98ab2077" />


### Advertising Effectiveness

Twitter is the most successful advertising channel overall

Followed by Instagram and Facebook

Bulk email surprisingly performs well among single customers

Brochure advertising is consistently the least effective

Figure 7: Advertising channel effectiveness

<img width="650" height="310" alt="Screenshot 2025-12-13 135545" src="https://github.com/user-attachments/assets/a7fd352c-f419-4159-9aa8-b9e4c540dded" />


# Recommendations

Increase inventory in high-revenue categories like Alcohol and Meat

Invest more in high-performing ad channels (Twitter, Instagram)

Scale back brochure advertising

Consider targeted bulk email campaigns for specific demographics

Reevaluate investment in underperforming markets like Montenegro

Tailor campaigns using customer segmentation by age, income, and education

# Next Steps

**Customer Segmentation:** Apply clustering techniques to identify distinct customer personas based on demographics and spending behaviour.

**Predictive Modelling:** Build models to predict customer response to advertising campaigns and future spending patterns.

**Advertising Attribution:** Improve ad exposure logic to correctly account for customers exposed to multiple channels.

**Automated Data Pipeline:** Replace manual Excel cleaning with a reproducible Python-based ETL process.

**Enhanced Dashboards:** Add more granualar views for product categories, demographics, and regional performance, including trend and forecast analysis.

**Statistical Validation:** Apply hypothesis testing to validate differences in spend across regions and customer segments.
