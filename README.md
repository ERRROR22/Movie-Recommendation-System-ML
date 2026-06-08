Content-Based Movie Recommendation System
A content-based movie recommendation system built using Python. This project utilizes Natural Language Processing (NLP) to parse movie details (overviews, genres, taglines, and keywords) and applies vectorization techniques to recommend visually and thematically similar movies based on a user's selection.

🚀 Features
Metadata Pooling: Combines movie overviews, genres, taglines, and keywords into a single comprehensive textual representation ("tags").
Text Preprocessing Pipeline: Cleans textual data by converting it to lowercase, removing punctuation, filtering English stopwords, and applying Lemmatization via NLTK.TF-IDF Vectorization: Transforms textual tags into numerical matrices utilizing bi-grams (ngram_range=(1,2)) to capture phrase context.
Cosine Similarity Mapping: Calculates spatial angles between feature vectors to return the top $N$ closest contextually matching recommendations in real-time.
Model Serialization: Automatically exports processed DataFrames, lookup indices, and weight matrices into portable pickle files for rapid deployment in web or mobile applications.

