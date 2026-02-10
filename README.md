# Big-data-LLM-project-distributed-retrieval-augmented-generation

---

## Repository Structure
```
├── dataset
│   ├── 5-nosql.pdf
│   ├── Finding Similar Items.pdf
│   ├── Recommender-Systems-[Netflix].pdf
│   ├── 2-spark.pdf

├── doc
│   ├── tasks.png
│   ├── retrieval and generation.png
│   ├── embeddings.png
│   ├── LLM generation.png

├── src
│   ├── retrieval.ipynb
│   ├── tokenizer.ipynb

├── README.md
 ```
## Project Overview

This project was developed as part of the course  
**INFO‑H‑515 – Big Data: Distributed Data Management and Scalable Analytics (ULB)**  
for the academic year **2024–2025**.

The objective is to design and implement a **Distributed Retrieval‑Augmented Generation (RAG) system**
for **automatic exam question generation from large-scale course materials**, leveraging distributed
data processing techniques and Large Language Models (LLMs).

---

## Focus on LLM‑Driven Retrieval‑Augmented Generation

A key emphasis of this project is the **integration of Large Language Models (LLMs)** within a
distributed data management pipeline.

Instead of directly prompting an LLM with raw documents, we adopt a **Retrieval‑Augmented Generation (RAG)**
approach, where:

1. Course materials (PDFs, slides, documents) are **distributedly ingested, preprocessed, tokenized, and embedded** using **PySpark**.
2. For a given user query (e.g., *“Generate exam questions on distributed data management”*), the system:
   - Retrieves the **Top‑N most relevant text chunks** using embedding‑based similarity search.
   - Ensures that the query and documents are embedded using the **same embedding strategy**.
3. The retrieved chunks are then used as **contextual input** to an **external LLM**, which generates
   **coherent, relevant, and course‑aligned exam questions**.

This design allows the LLM to focus on **reasoning and question generation**, while Spark handles
**scalability, parallelism, and data-intensive retrieval**.

---

## Key Contributions

- **Distributed RAG architecture** combining PySpark and LLMs.
- Support for **multiple embedding strategies** (e.g., TF‑IDF, Word2Vec, Sentence Transformers).
- Implementation of **similarity-based retrieval** (cosine, Euclidean, etc.) at scale.
- Careful handling of **LLM integration outside Spark executors** to avoid performance and execution issues.
- Analysis of **LLM context limitations** and strategies to control prompt size.
- Evaluation of both:
  - **Quality** of generated exam questions (relevance, clarity).
  - **Performance and scalability** of the distributed retrieval pipeline.

