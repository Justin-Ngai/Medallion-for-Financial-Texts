# Semi-structured data from Financial Modeling Prep

This repo is to record the development of a lakehouse on AWS that uses Financial Modeling Prep (FMP) data. The data will be semi-structured, AI agents will enhance it with metadata for other AI applications, and AI agents can answer questions about the articles.

**Q&A**

**Why FMP?** It’s used by credible organizations such as Citadel and Harvard.

**Why semi-structured data?** This is a balance between LLMs (unlike previous NLP) being better at handling text, and DW methodologies being built primarily on structured data.

**Developments**
- Built a Lambda function that gets FMP news articles and writes them to an S3 bucket
- Notebook that puts data into a DataFrame and uses a small language model to add more context
- Notebook that organizes the data into a star schema around company events (for signals)

**To do**
- Create a Bedrock agent that answers questions Create Bedrock agent that answers questions
