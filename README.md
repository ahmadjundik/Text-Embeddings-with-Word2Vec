# 📊 Vector Database Exploration using Word2Vec & Faiss

This repository contains my final project for the course **Big Data System Engineering & Organization** at Telkom University.  
The project explores the use of **Vector Databases** for similarity search on text reviews.

---

## 📌 Project Overview
The rapid growth of unstructured text data requires efficient ways to store, process, and retrieve information.  
This project focuses on building a **vector-based search engine** using:

- **Word2Vec** → for generating embeddings from text reviews  
- **Faiss (Facebook AI Similarity Search)** → for efficient similarity search on vector data  

Dataset used: **Disneyland Reviews** (42,000 reviews from Paris, California, and Hong Kong branches).  

---

## 📊 Dataset
- **Source**: TripAdvisor (*Disneyland Reviews dataset*)  
- **Size**: ~42,000 reviews  
- **Columns**:  
  - `Review_ID` → unique identifier  
  - `Rating` → 1–5 scale  
  - `Year_Month` → visit date  
  - `Reviewer_Location` → country of visitor  
  - `Review_Text` → review content  
  - `Disneyland_Branch` → branch location  

---

## ⚙️ Methodology
1. **Preprocessing**
   - Tokenization  
   - Removing stopwords  
   - Normalization (case-folding, removing diacritics)  

2. **Embedding with Word2Vec**
   - Trained using **Gensim**  
   - Vector size = 100  
   - Window = 5  
   - Architecture = Skip-gram  
   - Average vector per review  

3. **Vector Indexing with Faiss**
   - Built using `IndexFlatL2` (Euclidean distance)  
   - Enables fast similarity search across 42,000 reviews  

4. **Querying**
   - Convert user query → vector using Word2Vec  
   - Retrieve top-5 most similar reviews from Faiss index  

5. **Optimization**
   - With Faiss index → query runs in **milliseconds**  
   - Without Faiss (linear search) → ~34 seconds  

---

## 🏆 Results
- **Faiss index** significantly speeds up similarity search.  
- Retrieved results contain both positive & negative reviews, depending on query context.  
- Demonstrated how vector databases can handle **semantic similarity search** better than keyword-based search.  

---
