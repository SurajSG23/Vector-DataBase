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

# Vector Space

A **vector space** is a mathematical concept where **vectors live**.

* A **vector** is basically a list of numbers that represent **something in space**.
* A **vector space** is a set of these vectors where you can do **two main things** safely:

  1. **Add vectors together**
  2. **Multiply vectors by numbers (scalars)**

Think of it as a **playground for vectors** where all the rules of addition and scaling work.

---

### 🔹 Simple Example

Imagine 2D vectors:

* Vector A = `[2, 3]`
* Vector B = `[1, 5]`

In a vector space:

1. **Addition works:**

```
A + B = [2+1, 3+5] = [3, 8]
```

2. **Scalar multiplication works:**

```
2 * A = [2*2, 2*3] = [4, 6]
```

---

### 🔹 Why Vector Spaces Matter

* They help us **represent things as numbers** in a structured way.
* In **AI and vector databases**, vector spaces are used to represent **words, images, or documents as vectors**.
  Example:

  * “Cat” → `[0.2, 0.7, 0.1, ...]`
  * “Dog” → `[0.3, 0.6, 0.1, ...]`
  * “Car” → `[0.9, 0.1, 0.5, ...]`

Now, **vectors that are “close” in space mean the things are similar in meaning**.

---

### 🔹 Analogy

* Imagine each vector is a **point in space**.
* Vector space is like a **giant 3D or multi-dimensional map** where you can measure **distances between points**.
* Nearby points = similar meaning / related things.

---

Ah, got it! Let’s start **from the basics**.

---

# Distance Metric

A **distance metric** (or distance function) is a **way to measure how far apart two points or vectors are** in a space.

* In simple terms: it tells you **“how similar or different two things are”**.
* The smaller the distance → the more similar the points.
* The larger the distance → the more different they are.

---


## 1. Euclidean Distance (Straight-line distance)

* Think of it as **“as the crow flies”** between two points.
* Formula for vectors (A = [a_1, a_2, ..., a_n]) and (B = [b_1, b_2, ..., b_n]):

$$
\text{Euclidean Distance} = \sqrt{(a_1-b_1)^2 + (a_2-b_2)^2 + ... + (a_n-b_n)^2}
$$

* **2D Example:**
  A = `[3, 4]`, B = `[0, 0]`
  Distance = √((3−0)² + (4−0)²) = √(9 +16) = 5

*  Best for “real space” distances.

---

## 2. Manhattan Distance (City Block / Taxicab)

* Imagine moving **only along streets**, not diagonal — like in a city grid.
* Formula:

$$
\text{Manhattan Distance} = |a_1 - b_1| + |a_2 - b_2| + \dots + |a_n - b_n|
$$

* **2D Example:**
  A = `[3, 4]`, B = `[0, 0]`
  Distance = |3−0| + |4−0| = 3 + 4 = 7

* Good for high-dimensional spaces and certain AI problems.

---

## 3. Dot Product (Scalar / Inner Product)

* Measures **how much two vectors point in the same direction**.
* Formula:

$$
A \cdot B = a_1b_1 + a_2b_2 + ... + a_nb_n
$$

* **2D Example:**
  A = `[1, 2]`, B = `[3, 4]`
  Dot Product = 1×3 + 2×4 = 3 + 8 = 11

* **Interpretation:**

  * Large positive → vectors point in **similar directions**
  * 0 → vectors are **perpendicular (uncorrelated)**
  * Negative → vectors point in **opposite directions**

* Often used to compute **cosine similarity**:

[
\cos(\theta) = \frac{A \cdot B}{||A|| , ||B||}
]

where (||A||) is the vector’s length (Euclidean norm).
Cosine similarity = 1 → very similar, 0 → unrelated.

---

### Summary Table

| Metric          | Measures                   | Formula (2D/ND) | Use Case                          |   |                                     |
| --------------- | -------------------------- | --------------- | --------------------------------- | - | ----------------------------------- |
| **Euclidean**   | Straight-line distance     | √Σ(a_i-b_i)²    | Geometric distance, clustering    |   |                                     |
| **Manhattan**   | Grid / city block distance | Σ               | a_i-b_i                           |   | High-dimensional AI, sparse vectors |
| **Dot Product** | Alignment / similarity     | Σ(a_i * b_i)    | Cosine similarity, NLP embeddings |   |                                     |

---

### Analogy

* **Euclidean** → Fly from A to B directly
* **Manhattan** → Walk only along streets, no diagonals
* **Dot Product** → Compare **direction of two arrows**, not distance

---
