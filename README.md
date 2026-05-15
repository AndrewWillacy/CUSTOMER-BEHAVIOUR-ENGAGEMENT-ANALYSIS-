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

## Database Structure

The project uses two PostgreSQL tables:

**Marketing_Data**

Includes demographics, purchase details, and customer behaviour metrics such as:
Age, Income, Total_Spend, Education, Marital_Status, Country, Kids/Teens, product category spend, and more.

Figure 1: Marketing_Data Table
<img width="900" height="600" alt="Screenshot 2025-12-13 151717" src="https://github.com/user-attachments/assets/fc31ca9c-3dba-44e6-b499-d2c689e799ee" />

**ad_data**

Contains binary indicators showing whether a customer was exposed to each advertising channel:
Twitter, Instagram, Bulkmail, Facebook, Brochure

Figure 2: Ad_Data Table
<img width="900" height="300" alt="Screenshot 2025-12-13 151842" src="https://github.com/user-attachments/assets/0484f707-b2a5-4054-aeab-749ae308e73e" />

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

End-to-end data workflow · Data cleaning and validation · Exploratory analysis (EDA) · SQL database building & querying · Outlier detection and handling ·  Dashboard development · Business insight generation · Stakeholder-focused reporting · Data visualisation · Commercial analysis

---

## Analytical Approach

The project followed a structured multi-stage workflow combining data cleaning, exploratory analysis, SQL analysis, and dashboard development.The raw dataset required significant preparation before analysis could begin:

### 1. Data Cleaning & Validation (Excel)

The raw CSV datasets were initially imported into Excel for cleaning and preparation.

Key cleaning and validation steps included:

* Standardised date formatting:
standardised to DD/MM/YYYY
* Removal of duplicate records: rows with identical entities across all fields except PK removed as implausible duplicates
* Validation of primary key uniqueness: primary key (ID) checked for uniqueness
* Standardisation of text formatting and category labels: product category codes translated to meaningful labels (e.g. 'AmtLiq' → 'Alcohol')
* Identification and removal of implausible age records: three records showing customer ages over 124 removed as implausible; one income outlier of $666,666 (far above the next highest value) excluded from income-based analysis, but retained for other analyssis
* Handling of inconsistent marital status categories: 'Single' and 'Alone' merged; 'YOLO' and 'Absurd' removed (three records, negligible impact)
* Removal of formatting inconsistencies in income data: Formated column to numeric, removing $ signs and setting to 2 decimal places
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

Figure 3: The number of customers by country

<img width="750" height="450" alt="Screenshot 2025-12-13 134910" src="https://github.com/user-attachments/assets/e5d1c800-453f-48d9-80ae-5ae6a2a84731" />/

Figure 4: Incoome by total spend

<img width="650" height="420" alt="Screenshot 2025-12-13 135615" src="https://github.com/user-attachments/assets/45a9f51f-8882-4c0b-ad4d-1ec35ef3f1a8" />

---

### 3. SQL Analysis (PostgreSQL)

Following cleaning and exploratory analysis, a PostgreSQL database was created with two tables — `Marketing_Data` and `ad_data` — with customer ID as the primary key. 
The tables were populated by importing the csv files of the same names, for deeper analytical querying. Initially this was done on the individual tables and later they were joined to form a third table.

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
  
**Revenue and product analysis:**
- Total spend aggregated by country using `SUM` and `GROUP BY`
- Most and least popular product categories identified per country and marital status using `GREATEST` and `LEAST` functions within `CASE` statements
- Product preferences cross-referenced by household composition (kids/teens at home vs not)

**Advertising effectiveness:**
- Boolean ad exposure fields cast to integer to enable summation
- Most and least effective channels identified per country and marital status
- A `Media` column was engineered in `ad_data` to enable average spend analysis by channel — customers joined to their advertising exposure and average spend calculated per channel using `ROUND(AVG())` and `ORDER BY Avg_Spend DESC`

**Key SQL technique:** Boolean-to-integer casting (`::INT`) to aggregate advertising exposure data, and `GREATEST`/`LEAST` functions to identify highest and lowest values across multiple product or channel columns within a single query.

**Key SQL findings included:**

#### Product Performance

* Alcohol products accounted for approximately 50% of total product sales
* Meat products represented the second-highest revenue category
* Vegetables and chocolate generated the lowest sales performance
* Product preference patterns remained relatively consistent across customer demographics

#### Campaign Effectiveness

* Twitter (X) was identified as the highest-performing advertising channel
* Instagram and Facebook also demonstrated strong engagement performance
* Brochure advertising consistently underperformed across most demographic groups
* Bulk email campaigns showed stronger performance amongst single customers than expected

#### Geographic Performance

* Spain generated significantly higher total revenue than other regions
* Germany produced the highest average customer spend
* Montenegro significantly underperformed relative to all other markets

---

### 4. Dashboard Design & Development

The Tableau dashboard was designed with a non-technical executive audience in mind, using a calm blue colour scheme chosen for readability, accessibility and professionalism. Prototype layouts were planned on paper before build.


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

Design decisions prioritised clarity over complexity - filters allow stakeholder exploration without requiring analytical knowledge. Chart types were chosen to match the nature of each variable (bar charts for categories, scatter plots for continuous relationships, maps for geographic data).

Figure 5: Tableau Dashboard
<img width="900" height="600" alt="Screenshot 2025-12-13 153958" src="https://github.com/user-attachments/assets/685b0d12-1b62-406f-95fd-34674e667c78" />

---

## Key Findings & Business Recommendations

### Finding 1: Demographic Patterns Influenced Engagement Behaviour

Customer demographics demonstrated measurable differences in purchasing and campaign engagement behaviour.

Key observations included:

* Married and partnered customers formed the largest customer group
* Most customers were educated to graduate level or above
* The customer base spans 8 countries
* Customer age ranges from 28 to 84 (average 55)

#### Recommendations

> Use demographic segmentation to support more targeted and personalised marketing strategies.

---

### Finding 2: Product Sales Were Highly Concentrated

Alcohol products represented approximately half of all product sales, with meat products generating the second-highest revenue contribution.

| Product      | Category Insight                                                                  | Business Impact                    |
| ------------ | ----------------------------------------------------------------------------------|------------------------------------|
| Alcohol      | 50% of all sales — most popular in every country and across all marital statuses  | Core commercial revenue driver     |
| Meat         | Second highest sales overall                                                      | High-value supporting category     |
| Vegetables   | Consistently worst performing across all segments                                 | Potential optimisation opportunity |

Product preferences do **not** meaningfully vary by marital status, country, or whether children or teenagers are present in the household. Alcohol dominates universally.

#### Recommendations

> Prioritise inventory, promotions, and marketing activity around high-performing product categories (alcohol and meat) while reviewing the commercial viability of underperforming categories such as vegetables

---

### Finding 3: Social Media Significantly Outperformed Traditional Advertising

Twitter (X), Instagram, and Facebook consistently generated stronger campaign engagement than brochure-based advertising. 
Brochure advertising is the least effective channel across nearly every country and marital status segment — the only exception being Montenegro (two customers, statistically negligible).

Bulk email performs surprisingly well among single customers, approaching Twitter effectiveness for that demographic.


| Advertising Channel  | Relative Performance           |
| -------------------- | ------------------------------ |
| Twitter              | Highest-performing             |
| Instagram            | Strong                         |
| Facebook             | Strong                         |
| Bulk Email           | Effective for single customers |
| Brochure Advertising | Weakest-performing             |

Figure 6: Advertising channel effectiveness

<img width="650" height="310" alt="Screenshot 2025-12-13 135545" src="https://github.com/user-attachments/assets/a7fd352c-f419-4159-9aa8-b9e4c540dded" />

#### Recommendations

> Increase focus on digital and social media marketing while reducing reliance on lower-performing brochure campaigns  
> Prioritise Instagram and Twitter (X) for advertising investment — both drive the highest average customer spend  
> Discontinue or significantly reduce brochure advertising - consistently least effective across all segments  
> Target single customers with bulk email — disproportionately effective for this demographic
---

### Finding 4 Geographic Performance Varied Significantly

Although Spain generated the highest total revenue, Germany produced the highest average spend per customer.

| Country Insight                         | Commercial Interpretation |
| --------------------------------------- | ------------------------- |
| Spain generated highest total revenue   | Largest customer base     |
| Germany generated highest average spend | Higher customer value     |
| Montenegro significantly underperformed | Low commercial return     |

Figure 7: Average customer spend by country

<img width="650" height="400" alt="Screenshot 2025-12-13 135503" src="https://github.com/user-attachments/assets/b6d44b4d-d328-478a-939d-2bfd98ab2077" />

 Spain has by far the largest customer base (994 customers) and highest total revenue ($652,074), but Germany produces the highest average spend per customer ($694.50), followed closely by the USA ($689.07).

#### Recommendation

> Investigate Germany — smaller customer base but highest average spend per customer suggests high-value segment worth developing
> Review Montenegro — two customers and negligible revenue; assess whether to maintain or exit this market

---
## Limitations

Several limitations were identified during the analysis:

- **Income data inconsistency:** Income values appear to be a mix of annual and monthly figures; no normalisation was possible without additional context
- **Some demographic categories required manual standardisation:** eg Non standard entries for categories such as "Marital status"
- **15-year-old customer:** The youngest customer would have been 15 at registration — raises data collection questions that could not be resolved with available information
- **Spending score unknown:** No metadata explaining how `Count_success` was calculated — limits interpretation of campaign success metrics
- **Cross-sectional snapshot:** No time dimension in the data; trends over time cannot be assessed
- **Small advertising sample:** Only 292 customers were exposed to at least one advertising channel, limiting the statistical robustness of channel effectiveness conclusions
- **Single ad exposure assumed:** The methodology assigns one channel per customer based on the last Boolean flag set — customers exposed to multiple channels are not fully accounted for
- **The dataset represented historical behaviour only and could not fully predict future trends:** Insufficient data
- **Several low-volume geographic markets limited comparative analysis reliability:** Montenegro significantly small than Spain or Germany
- **Customer lifetime value and retention metrics were unavailable:** Not available in the data

Despite these limitations, the dataset was sufficiently robust to identify clear behavioural and commercial trends.

---

## Further Analysis

- **Customer segmentation modelling using clustering techniques:** Segmenting customers by age, income, marital status, education etc
- **Development of real-time dashboards in Power BI or Tableau:** Live updates to the database linked to real time dashboards
- **Longitudinal analysis:** Track how customer demographics and purchasing behaviour shift over time
- **Customer lifetime value (CLV) & churn analysis:** The net profit or revenue the business expects to earn per customer through the lifetime of the relationship. Churn value will predict how likely a customer is to stop using the business
- **Multi-channel exposure & A/B testing:** Properly account for customers exposed to more than one advertising channel to understand combined channel effects and test different ad media against each other
- **Country-level deep dive:** Explore why Germany produces higher average spend despite a smaller customer base
- **Age-segmented advertising analysis:** Test whether younger and older customer segments respond differently to specific channels
- **Income normalisation:** Clarify whether income figures are annual or monthly and normalise accordingly before including income in regression or clustering analysis
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

## Results Summary

| Question | Answer |
|----------|--------|
| Who are the customers? | Primarily aged 28–84 (avg 55), married/together, graduate-educated, concentrated in Spain |
| Which ad channel is most effective? | Instagram (highest avg spend $1,609); Brochure consistently least effective |
| Which products sell best? | Alcohol (50% of all sales) universally; no meaningful demographic variation |
| Does purchasing behaviour differ across demographics | Alcohol is the most popular product across all demographics - vegetables the least popular |
| Are there geographic differences in sales perfromance |Spain gebnerates the highest income from any country. Montenegro the least |


The primary objectives of the analysis were to:

* Understand purchasing behaviour across customer groups
* Explore geographic differences in customer behaviour and sales performance
* Provide actionable recommendations to improve marketing efficiency and commercial performance

---

## Repository Structure

```
Customer-Behaviour-Engagement-Analysis
├── 2Market Tableau Dashboard
│   └── Dashboard.md                       # Link to live Tableau dashboard 
├── CSV files
│   └── Files Cleaned
|       ├── marketing_data_cleaned.csv     # Cleaned marketing dataset
│       └── ad_data_cleaned.csv            # Cleaned advertising dataset
|   └──Files RAW data
│      ├── marketing_data.csv              # Raw marketing dataset
│      └── ad_data.csv                     # Raw advertising dataset
├── SQL Queries            
│   └── SQL Queries                        # SQL code for multipe queries used in the analysis
├── Presentation slides.pdf                # Presentation slide deck as pdf
├── README.md                              # Full analysis
├── Tableau Dashboard.twbx                 # Static Tableau dashboard (Can be opened with Tableau)
├── Technical Report.pdf                   # Technical report of analysis
├── metadata.txt                           # Metadata gives descriptions of all the fields in the tables

```

## About

This project was completed as part of the **LSE Data Analytics Career Accelerator (2025, Distinction)**.

The analysis focused on transforming raw customer and marketing data into actionable business insights through structured cleaning, exploratory analysis, SQL querying, and dashboard development.

**Andrew Willacy**
[LinkedIn](https://www.linkedin.com/in/andrew-willacy-572682347/) | [GitHub Portfolio](https://github.com/AndrewWillacy) | [andrew.willacy.data@gmail.com](mailto:andrew.willacy.data@gmail.com)

---



