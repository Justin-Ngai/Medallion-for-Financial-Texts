# Medallion Architecture for Extracting Alpha Signals from Financial News Articles

The purpose of this project is to build a production-ready medallion architecture that extracts alpha signals from Financial Modeling Prep (FMP) news articles. During the development, I learn about:
- Ingestion best practices using AWS Lambda functions
- Using AWS SageMaker Lakehouse and data agents, and how this compares to Microsoft Fabric and Databricks (both of which I'm certified for)
- Financial considerations for designing a semantic layer for alpha signals

Financial Modeling Prep was chosen because it's used by reputable companies, such as Citadel and Harvard. News articles were chosen because they're webpages (aka. semi-structured data), which are harder to standardize on vs tabular data.
