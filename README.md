# Ingestion and Staging of Financial Text Data

This project ingests financial text data from two sources:
- **Financial Modeling Prep (FMP)** — news articles
- **Alpha Vantage** — earnings call transcripts

The goal is to build an ingestion and staging layer that organizes raw, semi-structured text data into a medallion-style layout, suitable for downstream analysis.

## Scope

This project focuses on:
- ingesting text data using AWS Lambda and scheduled jobs
- staging semi-structured text data in AWS SageMaker Lakehouse
- organizing raw text into consistent schemas that support a basic semantic layer

## Data Providers

Financial Modeling Prep was selected because it is used by firms such as **Citadel** and **Harvard**. Alpha Vantage was selected for its coverage of earnings call transcripts.

Both providers expose text data in semi-structured formats.
