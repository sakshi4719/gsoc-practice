# BERT 
Explored sentiment analysis of Reddit post titles using a pre-trained BERT-based model.  
The `nlptown/bert-base-multilingual-uncased-sentiment` model from Hugging Face Transformers was used for this task.  
The dataset used was `reddit_data_not_processed.csv` which I had created for the test for AI-Powered Behavioral Analysis project.  
* The model processed each title for sentiment analysis.
* The output sentiment scores range from 1 to 5, representing star ratings.
    ``
    {0: '1 star', 1: '2 stars', 2: '3 stars', 3: '4 stars', 4: '5 stars'}
    ``
* The pandas dataframe is used to hold the data, and the Hugging face transformers library is used for the model and tokenizer.
* Pytorch is used to process the model.

# GeoPandas 
Performed spatial operations using GeoPandas and Descartes libraries. Used Matplotlib for some visualization.
* Reading shapefiles into Geopandas GeoDataFrames.
* Plotting GeoDataFrames with various styles and color maps.
* Plotting multiple GeoDataFrames side-by-side and overlaid.
* Checking and transforming Coordinate Reference Systems (CRS).
* Intersecting spatial layers using `gpd.overlay`.
* Calculating the area of intersected polygons.
* Exporting a GeoDataFrame to a shapefile.

# Plotly
Created various interactive plots to explore relationships between different variables in the Gapminder dataset, such as GDP per capita, life expectancy, population, and continent.
The dataset used was the Gapminder dataset (`px.data.gapminder()`)
### Visualization Types:
* Scatter plots (including size and color encoding)
* Scatter plots with facets (subplots)
* Line charts
* Bar charts
* Stacked bar charts
* Line charts comparing two countries
* Heatmaps
### Interactive Features:
* Hover data and hover names
* Interactive legends
* Customizable plot layouts and templates
* Text annotations on lines.


# Sentiment Analysis: VADER and TextBlob
Explored sentiment analysis using two popular Python libraries: TextBlob and VADER (Valence Aware Dictionary and sEntiment Reasoner).  
Compared the performance of TextBlob and VADER in sentiment analysis on positive and negative text samples.  
Datasets used were  
- `positive` (text file containing positive sentences)  
- `negative` (text file containing negative sentences)

### TextBlob
* Provides both polarity and subjectivity scores, which can be useful for filtering subjective sentences.
* Accuracy varies depending on the threshold used for polarity classification.

### VADER
* Offers a compound score that summarizes overall sentiment.
* Using a compound score threshold improves accuracy.
* Filtering based on conflicting sentiment scores can further refine classification.
* Specifically designed for social media text, and performs well on short phrases.

# Topic Modelling: LDA, Top2Vec, BERTopic
Explores topic modeling using three different techniques: Latent Dirichlet Allocation (LDA), BERTopic, and Top2Vec.   
Dataset used was a text dataset (`vol7.json`) using various topic modeling approaches and compare their results.   

### Latent Dirichlet Allocation (LDA)
Libraries: `gensim`, `spacy`, `nltk`, `pyLDAvis`
#### Preprocessing:
* Loading data from JSON.
* Lemmatization using spaCy.
* Tokenization using `gensim.utils.simple_preprocess`.
* Creation of a document-term matrix (corpus) and dictionary.  
#### Observations:
* LDA is a probabilistic topic model that infers topics based on word co-occurrence.
* Preprocessing steps like lemmatization are crucial for LDA's performance.
* `pyLDAvis` provides a useful way to explore and interpret LDA topics.

### BERTopic
Library: `bertopic`
#### Observations:
* BERTopic leverages transformer-based embeddings for topic modeling.
* It handles outliers effectively, assigning them to topic -1.
* BERTopic can work with stopwords, as it uses semantic meaning, not just word frequency.
* It produces semantically coherent topics.
* It can visualize topic clusters, and the most common words per cluster.

### Top2Vec
Library: `top2vec`
#### Observations:
* Top2Vec uses document embeddings to find semantically similar topics.
* It's robust to word variations and synonyms.
* It can retrieve relevant documents for each topic, ranked by similarity.
* Top2vec is based on semantic and syntactical understanding, which is much better than frequency based models.
