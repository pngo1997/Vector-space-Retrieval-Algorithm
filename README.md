# 🔍 Vector-space Retrieval & Mean Average Precision Evaluation  

## 📜 Overview  
This project implements the **Inverted Index Retrieval Algorithm** and evaluates retrieval performance using **Mean Average Precision (MAP)** on the **Medline Collection**, a benchmark dataset for Information Retrieval (IR) research.  

📌 **Dataset: Medline Collection**  
- **1,033 documents** (medical abstracts)  
- **30 queries**  
- **Relevance judgments** for query-document pairs  

📌 **Goals:**  
1. Implement **query-based document ranking** using the **Vector Space Model (VSM)**.  
2. Compute **cosine similarity** between queries and documents.  
3. Generate a **ranked list** of relevant documents.  
4. Evaluate retrieval effectiveness using **Mean Average Precision (MAP)**.  

📌 **Programming Language**: `Python 3`  
📌 **Libraries Used**: `NumPy`, `pandas`, `math`, `csv`  

## 🚀 Implementation Steps  

### **1️⃣ Load Index & Query Data**  
- Read and store **inverted index (`H_invindex`)** mapping **terms → (idf, postings)**.  
- Compute **document vector lengths (`DL_doclen`)** for normalization.  
- Load **queries (`Queries_list`)** as **(query ID, term frequency map)**.  

### **2️⃣ Compute Query Vector Lengths**  
- Calculate **query vector lengths (`L`)** using term frequencies and **inverse document frequencies (IDF)**.  
- Skip query terms **not found** in the vocabulary.  

### **3️⃣ Cosine Similarity & Ranking**  
- Compute **cosine similarity** between **query and document vectors**.  
- Rank documents **by descending similarity** for each query.  
- Store ranked results in **`rankedlist.txt`**.  

### **4️⃣ Evaluate Performance (MAP Calculation)**  
- Compare ranked results against **relevance judgments (`medline.rel`)**.  
- Compute **precision at each relevant document rank**.  
- Calculate **Mean Average Precision (MAP)** across all queries.  
