# FMP-semi-structured

This repo is to record the development of a lakehouse on AWS that uses Financial Modeling Prep data. The data will be semi-structured, AI agents will enhance is with metadata for other AI applications, and AI agents can answer questions about the articles.

**Q&A**

Why FMP? It's used by credible organizations such as Citadel and Harvard.

Why semi-structured data? This is a balance between LLMs (unlike previous NLP) being better at handling text, and DW methodologies being build primarily on structured data.

**Developments**

- Built a lambda function that gets FMP news articles and writes them to an S3 bucket
- Notebook that puts data into dataframe, uses small language model to add more context

**To do**
- Review cleaning
- Create agent that answers questions
