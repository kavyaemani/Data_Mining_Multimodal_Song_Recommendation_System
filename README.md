# Song Recommendation System: Final Project
This repository contains the implementation of a song recommendation system designed to suggest songs based on audio features, lyrical content, and emotional responses from listeners. The model integrates data from Spotify and YouTube to deliver personalized music recommendations.

# Project Objective
The primary objective of this project is to develop a recommendation system that can suggest songs based on the following attributes:
- Audio Features (e.g., Danceability, Energy, Tempo, Key, etc.)
- Lyrical Content (using Natural Language Processing techniques)
- Emotional Responses from listeners (scraped from YouTube comments)

# Datasets
We utilized two datasets for the project:
- Spotify Dataset: Includes song attributes (such as danceability, tempo, energy, etc.) and lyrics.
- YouTube Dataset: Includes top YouTube comments for each song, categorized based on the emotional responses of listeners (e.g., Humor, Empathy, Appreciation, etc.).
- Both datasets were merged using Spotify track IDs, with YouTube comment data providing emotional insights about songs.

# Methodology
- Data Preprocessing
  - Cleaned and merged the two datasets (Spotify and YouTube) based on song IDs.
  - Handled missing values and performed feature scaling for numerical features.
  - Used topic modeling for song lyrics to categorize songs based on themes (e.g., Love & Relationships, Self-Reflection, etc.).
- Model Development
  - Clustering:
    - Used clustering techniques to group songs based on audio features and emotional responses from YouTube comments.
    - Employed K-means to create 5 clusters that represent distinct groupings of songs.
- Recommendation System:
  - Used Euclidean Distance and Cosine Similarity to calculate song similarity.
  - Recommended songs based on the similarity to user-preferred songs.
- Classification Models:
  - Implemented multi-label, multi-class classification models to predict multiple labels (e.g., Humor and Energy) for each song based on features and comments.
  - Used Random Forest Classifier wrapped in MultiOutputClassifier for multi-label predictions.
- Evaluation:
  - Evaluated the performance of the models using accuracy, precision, recall, and F1-score for each label.
  - Generated classification reports for each label to assess the model's fairness across different emotional categories.
  - Fairness & Bias Analysis
  - Applied fairness metrics to evaluate how well the model performs for different groups (e.g., by gender, age group, or emotional response).
  - Used Fairlearn library to check for bias and fairness across the predicted labels.
- Visualizations:
  - t-SNE visualization to explore clusters in audio features.
  - Box plots to show the distribution of features across different clusters.
  - Accuracy charts for each label to compare model performance for emotional responses.
- Findings & Insights
  - The model successfully clusters songs based on their audio features and emotional responses.
  - Cluster 0: Higher concentration of humor and meme-related comments.
  - Cluster 1: Higher concentration of empathy-related comments.
  - Cluster 2: Lower concentration of comments across all emotional categories.
  - These insights helped improve the recommendation system by factoring in emotional responses to songs.
- Model Performance:
  - Accuracy by emotional response: The model performed better for categories like Words of Empathy (28.59%) and worse for categories like Personal Stories (23.96%).
# How to Run the Code
Clone this repository:
- git clone https://github.com/yourusername/song-recommendation.git
- cd song-recommendation
- Install required dependencies:
- pip install -r requirements.txt
- Run the Jupyter Notebook:\- Open the Jupyter notebook song_recommendation.ipynb.
- Challenges & Future Work
- Data Integration: Combining the datasets from Spotify and YouTube was challenging, especially ensuring that all song IDs matched across both platforms.
- Bias & Fairness: While the model showed high accuracy overall, there were some disparities in performance across different emotional categories. Future work could involve improving fairness by excluding certain sensitive features or using techniques like Adversarial Debiasing.
- Model Accuracy: There is still room to improve the accuracy for certain labels, which could be done by further tuning the hyperparameters or exploring other models like XGBoost or LightGBM.
# Conclusion
This project successfully integrates multiple sources of data to build a robust song recommendation system. By combining audio features, lyrics, and user sentiment, the system can offer diverse and personalized song recommendations. The use of multi-label and multi-class classification techniques ensures that a wide range of emotional tones are considered, making the system highly adaptable to individual preferences.

# References
Spotify & YouTube Datasets: Kaggle - Spotify & YouTube Data
Lyrics Dataset: Kaggle - Spotify Songs with Attributes and Lyrics
Fairlearn Library: Fairlearn Documentation
