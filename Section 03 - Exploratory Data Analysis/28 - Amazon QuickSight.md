# Amazon QuickSight - Must Know for AWS MLE Exam

Amazon QuickSight is a fully managed, serverless Business Intelligence (BI) and visualization service in AWS. It is designed for business users to easily create and share interactive dashboards and charts from a wide variety of data sources.

---

## Key Features & Properties
- **Serverless & Scalable:** Scales automatically from tens to tens of thousands of users without server management.
- **SPICE Engine:** Uses the Super-fast, Parallel, In-memory, Calculation Engine (SPICE) for extremely fast query performance. SPICE stores data in a columnar format and has a limit of ~10GB per user.
- **Data Connections:** Connects to Redshift, RDS, Aurora, Athena, S3 (Data Lakes), EC2-hosted databases, local files (CSV, Excel), SaaS (Salesforce), and any JDBC/ODBC-compliant databases.
- **Data Preparation:** Offers lightweight data prep capabilities (e.g., renaming fields, creating calculated fields, changing data types, and filtering data). *Not for heavy ETL—use AWS Glue for that.*
- **Security:**
  - Column-level security (Enterprise edition only) and Row-Level Security (RLS).
  - Private VPC access using ENIs and AWS Direct Connect.
  - User access managed via IAM, SAML SSO, email invites, or Active Directory (AD) integration.
  
---

## Machine Learning (ML) Insights
QuickSight features built-in ML Capabilities:
- **Anomaly Detection:** Powered by the Random Cut Forest (RCF) algorithm to detect outlier data points.
- **Forecasting:** Predicts key metrics with automatic seasonality detection, outlier handling, and imputation of missing values.
- **Auto Narratives:** Generates plain-language natural text summaries of insights from the charts.
- **QuickSight Q (Add-on):** Allows users to ask natural language questions (e.g., "What was our highest-selling product last quarter?") to generate visuals instantly. Requires setting up and training topics.

---

## Visualization Types & Use Cases

### 1. AutoGraph
- Automatically suggests the most appropriate visualization based on the data's properties and types.

### 2. Bar Charts (Vertical or Horizontal)
- Used for **comparison and distribution** of categorical or time-period data (e.g., comparing sales across different regions).

### 3. Line Charts (including Area and Stacked Area)
- Best for **showing trends or changes over time**. Area/Stacked Area charts show how different components add up to a total trend over time.

### 4. Scatter Plots
- Displays **correlation and distribution between two continuous variables** (e.g., comparing wait time vs. duration).

### 5. Heat Maps
- A color-coded 2D grid visualizing data intensity or value distributions (e.g., a reviewer rating matrix).

### 6. Pie and Donut Charts
- Show proportions or aggregation of categorical data relative to a total. Donut charts are cleaner when precision isn't critical.

### 7. Gauge Charts
- Visualizes a single measure relative to a target/goal (similar to a speedometer or fuel gauge).

### 8. Tree Maps
- Displays **hierarchical data as nested rectangles**, with sizes proportional to their values (e.g., export categories and subcategories).

### 9. Pivot Tables
- A tabular data aggregation tool that summarizes multi-dimensional data, allowing statistical functions to be applied at dimension intersections.

### 10. KPIs (Key Performance Indicators)
- Highlights key metric values compared directly to a set target or goal.

### 11. Geospatial Charts
- Maps with data points overlaid, where circle sizes typically represent the measure at that geographic location.

### 12. Word Clouds
- Visualizes the frequency of text data, where the size of each word corresponds to its frequency in the dataset.

---

## Dashboards vs. Analyses
- **Analyses:** The work area where you create and edit visuals, apply filters, and format charts.
- **Dashboards:** **Read-only snapshots** of an analysis. Dashboards are shared with other users who can view and interact with filters/controls, but **cannot edit** the underlying analysis.
- **Deprecated Feature:** **Stories** (previously a way to capture a sequence of dashboards) is now deprecated and no longer available.

---

## Exam Tips: Visualization Selection Cheat Sheet

When matching a dataset/question to a visual:
* **Changes/trends over time?** → *Line chart*
* **Comparing categories or distributions?** → *Bar chart*
* **Correlation between two continuous variables?** → *Scatter plot*
* **Proportions of a whole?** → *Pie/Donut chart*
* **Hierarchical categories?** → *Tree map*
* **Multi-dimensional tabular summaries?** → *Pivot table*
* **Comparing progress against a target?** → *KPI or Gauge chart*
* **Geographical data?** → *Geospatial chart*
* **Word frequency/Text data?** → *Word cloud*
* **Density/ratings matrix?** → *Heat map*
