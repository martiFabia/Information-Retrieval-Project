# Information Retrieval Project

This repository contains an end-to-end **Information Retrieval (IR)** system implemented in Python, developed as an academic project.

The project covers the full IR pipeline, from dataset loading and text preprocessing to index construction, compression, query processing, ranking models, and evaluation on a standard benchmark dataset.

---

## 📌 Project Overview

The main goal of this project is to design and analyze a scalable IR system, focusing on both **effectiveness** and **efficiency** aspects. In particular, the project explores:

* Construction of an **inverted index** from a large-scale dataset
* **Index compression** techniques to reduce memory footprint
* Different **query processing strategies** (TAAT, DAAT, and optimized variants)
* Comparison of classical **weighting models** such as TF-IDF and BM25
* Evaluation using standard IR metrics

The system is tested on the **MS MARCO Passage Dataset**, a widely used benchmark in modern information retrieval research.

---
> ⚠️ For full functionality, open it in Google Colab or JupyterLab.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1kZpJ08eJ87cFUHdFMF6pFj9_bc13WkRJ )

---

## 📂 Dataset

* **MS MARCO Passage Dataset**
* Millions of documents and a set of benchmark queries
* Due to computational constraints, the project focuses on efficient indexing and optimized query evaluation strategies

---

## 🛠️ Pipeline Structure

The notebook is organized into the following main sections:

1. **Environment Setup & Dependencies**
   Installation and configuration of required Python libraries.

2. **Dataset Loading**
   Loading documents and queries from MS MARCO.

3. **Text Preprocessing**
   A normalization pipeline applied consistently to documents and queries, including:

   * Lowercasing
   * Special character normalization
   * Tokenization

4. **Inverted Index Construction**

   * Lexicon creation
   * Posting lists generation
   * Document statistics computation

5. **Index Compression**
   Techniques to reduce index size while preserving retrieval effectiveness.

6. **Posting Lists Management**
   Efficient storage and access to term-document mappings.

7. **Query Processing**
   Implementation and comparison of:

   * **TAAT (Term-at-a-Time)**
   * **DAAT (Document-at-a-Time)**
   * Optimized TAAT with static pruning and accumulator pruning
   * **Optimized DAAT** with early termination and efficient accumulator management

8. **Ranking Models**

   * TF-IDF
   * BM25
   * Integration with **Query Expansion** techniques to improve recall

9. **Evaluation**
   Retrieval effectiveness evaluated using the `ir_measures` library, focusing on top-k metrics (e.g. k=10), including:

   * Precision
   * Recall
   * MRR
   * nDCG

---

## ⚙️ Optimization Techniques

To handle the scale of the MS MARCO dataset efficiently, the project introduces:

* **Static pruning** based on IDF ordering
* **Accumulator pruning** to limit unnecessary score updates
* **Optimized DAAT processing**, reducing the number of document score evaluations
* Efficient reuse of pre-built index structures to avoid repeated expensive computations

These optimizations significantly improve query processing speed while maintaining competitive retrieval quality.

---

## 📊 Key Comparisons

* **BM25 vs TF-IDF**: impact of term saturation and document length normalization
* **TAAT vs DAAT**: efficiency trade-offs in large-scale retrieval
* Optimized TAAT vs optimized DAAT
* Retrieval performance **with and without Query Expansion**

---

## 🚀 How to Run

1. Clone the repository
2. Open the notebook in Jupyter or Google Colab
3. Run cells sequentially (index building is executed once and reused)

> ⚠️ Note: Full indexing of MS MARCO is computationally expensive. The notebook is structured to avoid rebuilding the index at every run.

---

## 👥 Authors

* M. Fabiani
* T. Falaschi
* A. Franchini
* **R. A. Sacco**

