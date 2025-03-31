AstraDB Schema Definition

Database:
twitter_analysis

Keyspace:
customer_tweets_chunk

Collection:
customer_tweets

Fields in Collection:

| Field Name     | Type           | Description                                                              |
|----------------|----------------|--------------------------------------------------------------------------|
| `_id`          | `string`       | Auto-generated unique identifier for each record                         |
| `page_content` | `string`       | Tweet chunk text (used for vector search and retrieval)                  |
| `$vector`      | `vector[1536]` | Vector embedding generated from OpenAI for each `page_content` text     |
| `metadata`     | `object`       | Original tweet fields (tweet_id, author_id, created_at, etc.) as JSON    |

 Vector Configuration:
- Dimensions: 1536 (from OpenAI `text-embedding-ada-002` model)
- Similarity Metric: Cosine
- Vector Field: `$vector`
- Text Field for Context Retrieval: `page_content`

Notes:
- The text chunks were preprocessed from full tweets and stored in the `page_content` field.
- Vectors were generated using Langflow's OpenAI Embedding node.
- Vector search and retrieval are performed using AstraDB Hybrid Search via Langflow RAG workflow.
