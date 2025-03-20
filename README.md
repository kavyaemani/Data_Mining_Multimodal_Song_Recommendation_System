# Personalized Song Recommendation System

## Overview

The Personalized Song Recommendation System aims to recommend songs based on both audio features and emotional responses from listeners. The project utilizes data mining techniques, such as clustering and multi-label/multi-class classification, to provide personalized song suggestions.

## Project Objectives

- **Song Recommendation**: Recommend songs that align with individual preferences based on audio features and emotional responses.
- **Multi-label, Multi-class Classification**: Predict multiple emotional labels for each song based on its audio features and lyrical content.

## Datasets

1. **Primary Dataset (Spotify Song Attributes)**:
   - Contains metadata for songs, including attributes like artist name, song name, album, energy, danceability, loudness, and others.
   - Includes lyrics for each song.

2. **Secondary Dataset (YouTube Comments)**:
   - Scraped using the YouTube API, includes user comments on songs categorized into emotional response categories like humor, empathy, personal stories, etc.

## Methodology

1. **Data Preprocessing**:
   - Filtered English songs and handled missing values.
   - Merged datasets from Spotify and YouTube based on song ID.

2. **Clustering**:
   - Applied Agglomerative Clustering on both audio features and comment categories to identify meaningful clusters based on similarity.
   - Explored clustering algorithms like DB-Scan, K-Means, and Agglomerative clustering for better insights into the data.

3. **Recommendation System**:
   - Song recommendations are based on Euclidean distance, considering both audio features and emotional responses.
   - Used multi-label and multi-class classification to predict audience responses.

4. **Evaluation**:
   - Evaluated model performance using metrics like Subset Accuracy and Micro F1-Score.

## Key Findings

- **Clustering**: The dataset formed meaningful clusters based on similarities in audio characteristics and emotional responses.
- **Recommendations**: The system recommends songs by calculating similarity using Euclidean distance, offering personalized suggestions based on the selected song.
- **Classification**: Applied multi-label and multi-class classification to predict emotional labels for each song based on comments and audio features.

## Usage

### Cloning the Repository

```bash
git clone https://github.com/your-username/song-recommendation-system.git
cd song-recommendation-system
```

### Installing Dependencies

```bash
pip install -r requirements.txt
```

### Running the Project

To run the recommendation system:

```bash
python recommend_songs.py
```

This will prompt you to input a song, and the system will return the top 5 similar songs based on audio features and emotional responses.

## Files

- `spotify_youtube_comment_88247.csv`: Contains comments scraped from YouTube with likes.
- `df_final_aggregated.csv`: Contains aggregated Spotify metadata and comment categories.
- `recommend_songs.py`: Script to run the recommendation system.

## Libraries Used

- **openai**: For working with LLMs for comment categorization and topic modeling.
- **pandas**: For data manipulation and analysis.
- **sklearn**: For machine learning algorithms like clustering and classification.
- **matplotlib**: For visualizations.

## Conclusion

The project successfully developed a song recommendation system using both audio features and user-generated comments. It provides personalized recommendations by considering emotional responses and metadata, demonstrating the effectiveness of combining multi-label and multi-class classification techniques.

