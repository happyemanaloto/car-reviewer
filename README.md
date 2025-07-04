    
    Troubles in uploading the files. Kindly follow these instructions to construct the folder tree.
    Create folder ai-reviewer which has data, and notebooks
    Final dataset should be saved as: ai-reviewer/data/enriched_with_clusters_deployment.csv
    
        To generate this data using the notebook: Download datasets from https://www.kaggle.com/datasets/ankkur13/edmundsconsumer-car-ratings-and-reviews?utm_source=chatgpt.com and store in ai-reviewer/data/original/. Enrichment dataset came from https://www.kaggle.com/datasets/ademboukhris/expert-car-reviews-dataset?utm_source=chatgpt.com and should be saved in ai-reviewer/data/
        'ai_reviewer_main.ipynb' ==> is the notebook which holds it all
    
    app.py should be in ai-reviewer/
    So is the picture for the background, ai-reviewer/Background.jpg

    Steamlit should be run in terminal with command: streamlit run app.py
    
    This project provides an overview of this car-reviewer project.
    
    The 'ai_reviewer_main.ipynb' notebook's goal is to recommend the top 3 cars based on user preferences by leveraging data cleaning, 
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
