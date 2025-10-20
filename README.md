# 📚 Amazon Kindle Book Reviews – Sentiment Analysis  

## 🧾 Project Overview  
This project performs sentiment analysis on a subset (12,000 records) of the Amazon Kindle Store review dataset. The goal is to classify reviews as **positive (1)** or **negative (0)** based on the review text. The workflow includes data preprocessing, feature extraction (BoW & TF-IDF), and model training using Naive Bayes.  

---

## 📂 Dataset Information  

**Source:** Amazon Kindle Store (5-core dataset, May 1996 – July 2014)  
**Reference:** Julian McAuley, UCSD – http://jmcauley.ucsd.edu/data/amazon/  

### ✅ Columns Used  
| Column Name      | Description                                      |
|------------------|--------------------------------------------------|
| `reviewText`     | Main text of the review                         |
| `rating`         | Numerical product rating (1–5 stars)            |

After binary conversion:  
- **Positive (1):** Ratings ≥ 3  
- **Negative (0):** Ratings < 3  

---

## 📊 Dataset Summary  

| Rating | Count |
|--------|-------|
| 5      | 3000  |
| 4      | 3000  |
| 3      | 2000  |
| 2      | 2000  |
| 1      | 2000  |

**Final Dataset Shape:** `(12000, 2)`  

---

## ⚙️ Workflow & Best Practices  

### **1. Data Preprocessing & Cleaning**
- Convert text to lowercase  
- Remove special characters, stopwords, HTML tags, URLs  
- Apply tokenization and lemmatization  
- Convert ratings to binary labels (1 = positive, 0 = negative)

### **2. Feature Extraction**
| Technique      | Purpose                                   |
|----------------|-------------------------------------------|
| Bag of Words   | Converts text to token count matrix       |
| TF-IDF         | Converts text to term frequency-inverse document frequency |
| Word2Vec       | *(Planned)* Better for large datasets     |

### **3. Train-Test Split**
- 80% Training data  
- 20% Testing data  

### **4. Model Training**
- **Algorithm:** Gaussian Naive Bayes (works well on sparse matrices)

### **5. Evaluation Metrics**
```text
BOW Accuracy   : 0.5825  
TF-IDF Accuracy: 0.5808
```

## 🛠 Project Structure
```
├── all_kindle_review.csv       # Raw Dataset  
├── sentiment_analysis.ipynb    # Notebook with code  
├── README.md                   # Project documentation  
```

## 🚀 Future Enhancements

- Implement Word2Vec / GloVe embeddings
- Use LSTM, GRU, Bi-LSTM, or BERT models
- Visualize data using word clouds and confusion matrices
- Perform hyperparameter tuning for better accuracy

## 📜 Acknowledgements

**Dataset by:**

- Julian McAuley, University of California San Diego (UCSD)
- Amazon Product Data Repository
- All rights to dataset belong to the original authors

  
