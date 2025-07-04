    This project provides an overview of this car-reviewer project.
    'ai_reviewer_main.ipynb' ==> is the notebook which holds it all
    
    The notebook's goal is to recommend the top 3 cars based on user preferences by leveraging data cleaning, 
    sentiment analysis, topic modeling, clustering, summarization using gpt and a prototype deployment setup.
    The notebook uses MLflow to track experiments and log metrics.
    
    Data Sources: Primary datasets include 'all_sampled_cars.csv' and 'hour2_cardiff_sentiment.csv'.
    Cleaning Steps: Columns are standardized, missing values handled, and text fields prepared for analysis.

    Data Enrichment:
    Merging: Reviews and vehicle details are merged into a unified DataFrame.
    Feature Extraction: Regular expressions parse 'vehicle_title' to extract year, make, and model of each car.

    Sentiment Analysis:
    Pipeline Setup: A three-way sentiment analysis pipeline is built using Hugging Face transformers.
     
    Topic Modeling and Clustering
    TF-IDF Vectorization: Review texts are vectorized to capture term importance.
    Dimensionality Reduction: Truncated SVD reduces the vector space for efficient clustering.
    Clustering: KMeans (k=7) groups make-model combinations based on topic-count distributions.
    
    Based on selected topics and clusters, the system ranks and selects the top 3 cars.
    Deployment Stub: 
    Includes a Streamlit app scaffold and integration point with OpenAI GPT-3.5-turbo for user interaction.
    Cluster Insights: The seven clusters align with user concerns such as comfort, performance, reliability, 
    and design.
    Sentiment Trends: Positive sentiment dominates clusters associated with high user satisfaction.
    
    Output: The prototype successfully identifies top make-model combinations tailored to user-selected preferences.
