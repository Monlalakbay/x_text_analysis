# 🐦 Twitter/X Data Analysis Pipeline

![Python](https://img.shields.io/badge/python-3.9%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![NLP](https://img.shields.io/badge/NLP-SpaCy%2FBERTopic-green)
![License](https://img.shields.io/badge/License-MIT-blue)

A comprehensive pipeline for analyzing Twitter/X data using advanced NLP and machine learning techniques, featuring both traditional LDA and state-of-the-art BERTopic modeling.

---

## ✨ Features

### 🧹 Data Preprocessing
- Automated cleaning of raw Twitter/X data using *Instant Data Transfer*
- Handling missing values and duplicates
- Standardization of engagement metrics (K/M to numeric)
- Intelligent datetime parsing (relative and absolute formats)
  
### 📊 Exploratory Analysis
- Media engagement analysis (images vs. links vs. plain text)
- User activity profiling (most active, most engaging)
- Temporal analysis of tweet patterns

### 🧠 NLP Pipeline
- **Text Normalization**:
  - Lowercasing and special character removal
  - Emoji and URL removal
  - Custom stopword filtering
- **Advanced Processing**:
  - Spelling correction 
  - Lemmatization with POS tagging
  - Bigram/trigram detection

### 🤖 Topic Modeling
| Feature          | LDA (Gensim) | BERTopic |
|------------------|--------------|----------|
| Approach         | Bag-of-Words | Embeddings |
| Visualization    | pyLDAvis     | Plotly   |
| Temporal Analysis| ✅           | ✅       |
| Custom Stopwords | ✅           | ✅       |

---
    
## 🛠 System Requirements

### Hardware
- Minimum: 8GB RAM (for small datasets <5,000 tweets)
- Recommended: 16GB+ RAM (for full 10,000+ tweet analysis)
- GPU: Optional but recommended for BERTopic

### Software
- Python 3.9+
- Jupyter Lab/Notebook
- Input file: `x.csv` (10,000+ tweets mined on **05/03/2025** using *Instant Data Transfer*)
  - Tweet metadata (timestamp, engagement metrics)
  - Text content
  - Media attachments
  - User information

---

## ⚙️ Installation

1. Clone repository
```shell
git clone https://github.com/Monlalakbay/x_text_analysis.git
```
```shell
cd x_text_analysis
```

2. Create and activate virtual environment
```shell
python -m venv .venv
```
```shell
source .venv/bin/activate  # Linux/Mac
.venv\Scripts\activate     # Windows
```

3. Install dependencies
```shell
pip install -r requirements.txt
```

4. Download language models
```shell
python -m spacy download en_core_web_sm
```
```shell
python -m nltk.downloader punkt
```

---

## 🚀 Usage
1. Download or clone the X Text Analysis notebook folder.

2. Use the x.csv in the root directory or place your Twitter/X data (exported from Instant Data Transfer).

3. Launch Jupyter Notebook or Jupyter Lab.

4. Run through the notebook cells sequentially.

5. View generated visualizations. 

---

## 📂 Outputs

-Visualizations

-Engagement trends

-User activity charts

-Topic modeling results (LDA and BERTopic)

---

## ⚡ Configuration
Customize analysis in the notebook's configuration cell:

- `NUM_TOPICS = 8` – Number of topics for LDA/BERTopic  
- `MIN_TOPIC_SIZE = 50` – Minimum tweets per topic cluster  
- `TIMEZONE = "UTC"` – Timezone for datetime normalization  
- `CUSTOM_STOPWORDS = ['tourism', 'vacation']` – Add domain-specific stopwords
- `Min_df=5` – Ignores rare terms that appear in fewer than n tweets
- `Max_df=0.7` – Ignores overly common terms that appear in more than n% of the tweets

---


### 💡 Expert Tips

For Large Datasets (>10k tweets)
1. Memory Management:

- Restart kernel between major sections

- Use gc.collect() after memory-intensive operations
  

2. Performance:

- Enable GPU for BERTopic (torch.cuda.is_available())

- Reduce batch size in embedding generation
  

3. Quality:

- Adjust MIN_TOPIC_SIZE based on dataset size

- Review custom stopwords for your domain

