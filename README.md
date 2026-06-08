\# Movie Recommendation System







A content-based movie recommendation system built using Python. This project utilizes Natural Language Processing (NLP) to parse movie details (overviews, genres, taglines, and keywords) and applies vectorization techniques to recommend visually and thematically similar movies based on a user's selection.







\## 🚀 Features



\* \*\*Metadata Pooling\*\*: Combines movie overviews, genres, taglines, and keywords into a single comprehensive textual representation ("tags").



\* \*\*Text Preprocessing Pipeline\*\*: Cleans textual data by converting it to lowercase, removing punctuation, filtering English stopwords, and applying Lemmatization via NLTK.



\* \*\*TF-IDF Vectorization\*\*: Transforms textual tags into numerical matrices utilizing bi-grams (`ngram\_range=(1,2)`) to capture phrase context.



\* \*\*Cosine Similarity Mapping\*\*: Calculates spatial angles between feature vectors to return the top $N$ closest contextually matching recommendations in real-time.



\* \*\*Model Serialization\*\*: Automatically exports processed DataFrames, lookup indices, and weight matrices into portable pickle files for rapid deployment in web or mobile applications.







\---







\## 🛠️ Tech Stack \& Libraries



\* \*\*Language\*\*: Python 3



\* \*\*Data Manipulation\*\*: `pandas`, `numpy`



\* \*\*Visualization\*\*: `seaborn`, `matplotlib`



\* \*\*Natural Language Processing\*\*: `nltk`, `re`



\* \*\*Machine Learning \& Similarity\*\*: `scikit-learn`



\* \*\*Model Persistence\*\*: `pickle`, `ast`







\---







\## 📂 System Architecture \& Workflow







\### 1. Data Cleaning \& Null Treatment



\* Loaded the TMDB 5000 Movies dataset.



\* Removed duplicate row occurrences and reset the structural dataframe index.



\* Sanitized missing data records within the target features (e.g., filling empty `tagline` arrays with blank spaces).







\### 2. Feature Engineering (`tags`)



The recommendation core merges columns into a unified semantic profile block:



```python
df\['tags'] = df\['overview'] + " " + df\['genres'] + " " + df\['tagline'] + " " + df\['keywords']


3\. NLP Text Preprocessing Pipeline

Every pooled tag block goes through a structured purification pipeline:

Case Normalization: String components are uniformized to lowercase.

Noise Filtering: Regular expressions isolate structural alphabet strings, removing special characters and numeric noise.

Stopword Exclusion: Drops generic linguistic filler words (via nltk.corpus.stopwords).

Word Lemmatization: Inflected word forms are mapped back to their base dictionary lemma using the WordNetLemmatizer.

4\. Vectorization \& Computing ProximityThe system initializes a Term Frequency-Inverse Document Frequency framework bounded up to $50,000$ high-frequency feature parameters.
&#x20;


💻 Sample Output Evaluation

When querying the algorithm for sequels or highly correlated cinematic styles, the matrix outputs a prioritized list of closest relative coordinate

Query Example:
recommend('Captain America: Civil War', n=5)


Recommendation Engine Results:

Avengers: Age of Ultron

Captain America: The Winter Soldier

Iron Man 2

Iron Man 3

The Avengers

📦 Exported Assets for Deployment

The script serializes the following key artifacts to disk for pipeline persistence:

tfidf\_matrix.pkl: The computed sparse feature weights matrix.

indices.pkl: Reverse key-value lookup mapping dictionary (title -> index).

df.pkl: Cleaned structural metadata schema dataframe.

tfidf.pkl: Fitted vocabulary pipeline configuration vectorizer.

Developed by: Ritik Sharma
