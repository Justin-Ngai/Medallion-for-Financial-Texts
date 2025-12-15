# Medallion Architecture for Extracting Alpha Signals from Financial News Articles

The purpose of this project is to build a production-ready medallion architecture that extracts alpha signals from Financial Modeling Prep (FMP) news articles. During the development, I learn about:
- Production features for AWS Lambda functions
- Developing with AWS SageMaker Lakehouse and calling data agents. How this compares to Microsoft Fabric and Databricks - both of which I'm certified for.
- Reorganizing data for a semantic layer that financial analysts can query from

Financial Modeling Prep was chosen because it's used by reputable companies, such as Citadel and Harvard. News articles were chosen because they're webpages (semi-structured data), which are harder to standardize on than tabular data.
