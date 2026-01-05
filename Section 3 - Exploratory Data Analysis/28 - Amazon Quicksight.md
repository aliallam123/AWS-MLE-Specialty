# Amazon QuickSight - Must Know for MLE exam

- QuickSight = serverless BI & visualization service in AWS  
- Made for business users, not devs (easy dashboards, charts from many data sources)  
- Connects to: Redshift, RDS, Aurora, Athena + S3 datalake, EC2 DBs, files (CSV/Excel), SaaS (Salesforce), any JDBC/ODBC DB  
- Can do limited data prep: rename fields, calculated fields, change data types, SQL queries  
- Uses **SPICE** engine = fast, in-memory, columnar storage to speed queries  
- Scales to 100k+ users, SPICE per user limit ~10GB  
- Use cases: ad hoc interactive analysis, dashboards, KPIs, basic reports  
- ML Features (Machine Learning Insights):  
  - **Anomaly detection** (random cut forest)  
  - **Forecasting** (with seasonality, missing value imputation, outlier removal)  
  - **Auto narratives** (auto-generated plain language summaries of insights)  
- QuickSight Q (add-on):  
  - NLP powered business Q&A (ask questions in natural language)  
  - Requires personal training to setup topics & data for NLP  
- Paginated reports (new): multi-page printable reports from dashboards (check exam version for coverage)  
- NOT for heavy ETL (use Glue for that)  
- Security:  
  - MFA, VPC access (allow QuickSight IPs), Row Level Security (RLS), Column Level Security (enterprise only)  
  - Private VPC access via ENI + Direct Connect possible  
  - User management via IAM, email invites, SAML SSO, AD integration (enterprise edition)  
- Charges per user - control access to avoid excess cost  

*Summary:* QuickSight = user-friendly visualization + basic ML insights + scalable + secure, integrates with many AWS data sources, limited ETL, ML-powered Q&A available as paid add-on.
