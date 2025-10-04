# Vector Database

A **Vector Database** stores and searches data based on **meaning** — not just exact values.

It stores **vector embeddings** — which are **numerical representations of text, images, or audio** that capture their **semantic meaning** (how similar or related they are).

So instead of asking:

> “Find records where name = ‘Suraj’”

You can ask:

> “Find texts similar in meaning to this sentence”

It’s used in **AI, NLP, and RAG (Retrieval-Augmented Generation)** systems for semantic search, recommendation, or chatbot memory.

---

### Comparison: SQL vs NoSQL vs Vector DB

| Feature           | **SQL (Relational DB)**           | **NoSQL (Non-Relational DB)**      | **Vector DB**                                           |
| ----------------- | --------------------------------- | ---------------------------------- | ------------------------------------------------------- |
| **Data Type**     | Tables (rows & columns)           | JSON, key-value, document, graph   | Vectors (arrays of numbers)                             |
| **Schema**        | Fixed schema                      | Flexible / dynamic schema          | No fixed schema (stores embeddings)                     |
| **Query Type**    | Exact match, joins, filters       | Key-based or document queries      | Similarity search (find closest vectors)                |
| **Example Query** | `SELECT * FROM users WHERE id=1;` | `db.users.find({ name: "Suraj" })` | “Find vectors similar to this embedding”                |
| **Use Case**      | Banking, transactions, inventory  | Social media, e-commerce, logs     | AI search, chatbots, recommendations                    |
| **Examples**      | MySQL, PostgreSQL                 | MongoDB, Cassandra, Firebase       | Pinecone, Weaviate, FAISS, Chroma                       |
| **Scaling**       | Vertical (add more power)         | Horizontal (add more servers)      | Built for horizontal scaling and fast similarity search |

---

### Simple Analogy

* **SQL** → Like a spreadsheet with strict columns (good for structured data).
* **NoSQL** → Like folders of JSON files (good for flexible or large data).
* **Vector DB** → Like a smart memory that finds *similar* things instead of exact matches.

---
