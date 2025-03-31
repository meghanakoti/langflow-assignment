# GenAI Twitter Support Analyzer (Langflow + AstraDB)

This assignment implements a GenAI-powered data pipeline using **Langflow** and **AstraDB** to analyze customer support tweets. The system uses vector search with OpenAI embeddings and Retrieval-Augmented Generation (RAG) to answer user queries.

---

##  Assignement Goals

- Ingest unstructured tweet data
- Vectorize using OpenAI embeddings using langflow
- Store in AstraDB vector database
- Query with natural language using Langflow's RAG workflow

---

##  Files Included

| File | Description |
|------|-------------|
| `chunked_tweets2.csv` | Preprocessed tweet chunks for ingestion |
| `dataingestion.py` | Python script used to chunk the tweet data |
| `tweets_retrieval_workflow.json` | Exported Langflow workflow for vectorization (vectorization pipeline) |
| `tweets_retrieval_workflow.json` | Exported Langflow workflow for query retrieval (RAG pipeline) |

| `astra_schema.md` | Notes on AstraDB schema setup (keyspace, collection, etc.) |

---

## Dataset Used

**Customer Support on Twitter**  
https://www.kaggle.com/datasets/thoughtvector/customer-support-on-twitter

---

## Running the Langflow Workflow

> API Keys are **not included** in the `.json` file.  
> You’ll need to plug in your **OpenAI API key** and **Astra DB token** manually inside Langflow UI.

1. Import the JSON into Langflow.
2. Paste your API keys in the OpenAI and AstraDB nodes.
3. Run the workflow using the Playground.

---

## Sample Queries

- What are customers complaining about?
- What problems are users facing with their apps?
- How do companies respond to customer concerns?
- What kind of issues are people reporting with SprintCare?

---

## Setup Notes

- Developed and tested using [Langflow](https://docs.langflow.org/)
- AstraDB collection: `customer_tweets`  
  Keyspace: `customer_tweets_chunk`
- OpenAI model used: `text-embedding-ada-002`, `gpt-3.5-turbo`

--- 

