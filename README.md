# Article-Similarity-Network-NLP
NLP-based similarity analysis of news articles using TF-IDF, Cosine Similarity, and graph-based community detection to identify related content and key central articles.

In this project, I analyze relationships between news articles based on their textual content. Using **TF-IDF** for vectorization and **Cosine Similarity** for measuring similarity, I identify articles that are closely related in meaning and structure. I then translate these relationships into a graph structure to discover patterns such as clusters and central influential articles.

This approach helps enable:

✔ Better content organization  

✔ Recommendation of related articles  

✔ Identification of topic clusters  

---

## Data Preprocessing

I performed several NLP preprocessing steps:

- Removal of stop words, punctuation, and special characters  
- Tokenization of text into word tokens  
- TF-IDF vectorization to create numerical feature representations  

---

## Similarity Computation

I computed **Cosine Similarity** between TF-IDF vectors to measure article relatedness.

Similarity score ranges:
- **1.0** → identical meaning  
- **0** → completely unrelated  

To handle memory efficiently, I calculated pairwise similarity in batches.

📌 Example Result — Top 5 similar articles to Article **208866**:

| Article ID | Similarity Score |
|------------|-----------------|
| 208866 | 1.0000 |
| 68854 | 0.6703 |
| 67801 | 0.5990 |
| 72464 | 0.5987 |
| 97116 | 0.5954 |

---

## Graph Construction

To convert similarity into a network graph:

- Each **article is represented as a node**
- An **edge connects two articles** if similarity > **0.7**
- Edge weight = cosine similarity value

This network structure allows deeper relationship insights.

---

## Community Detection + Centrality Analysis

To understand topic-based groupings and influence:

| Technique | Purpose |
|----------|---------|
| **Louvain Algorithm** | Detect strong content-based communities |
| **Degree Centrality** | Identify most directly connected articles |
| **Betweenness Centrality** | Identify key articles linking different topics |

Graph visualizations produced using **NetworkX** + **Matplotlib**

---

## Requirements

Install dependencies using:

```txt
python>=3.8
pandas
numpy
scikit-learn
matplotlib
networkx
nltk
