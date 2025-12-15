# Medallion architecture for FMP news articles

This repo is to record the development of a medallion architecture on AWS for Financial Modeling Prep (FMP) news articles. 

FMP is used because it's also used by credible organizations such as Citadel and Harvard.

News articles are used because they're semi-structured data. This is a balance between LLMs being capable of processing unstructured data, and DW methodologies on structured data.

Files in this repo are:
- Sample news articles
- Python file for a lambda function that takes articles from FMP and puts into S3
- Notebook that stores these in an Apache iceberg format then uses a small language model to add more context
- Notebook that reorganizes the data into a star schema around company events (for signals)

**To do**
- Create a Bedrock agent that answers questions Create Bedrock agent that answers questions
