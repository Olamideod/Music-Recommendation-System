markdown_content = """
# Music Recommender System

## Overview

This project is a music recommender system built using Python, Streamlit, and Spotipy. The system allows users to discover new music similar to their favorite songs by providing personalized recommendations.

## Features

- **Selection Interface:** Users can select a song from a dropdown menu containing a list of available songs.
- **Recommendation Generation:** Upon selecting a song and clicking the "Show Recommendation" button, the system generates recommendations based on the similarity of the selected song to other songs in the dataset.
- **Display of Recommendations:** The system displays the top 5 recommended songs along with their album covers.

## How to Use

1. **Installation:**
   - Clone this repository to your local machine:
     ```
     git clone https://github.com/your_username/music-recommender.git
     ```
   - Navigate to the project directory:
     ```
     cd music-recommender
     ```
   - Install the required dependencies:
     ```
     pip install -r requirements.txt
     ```

2. **Running the App:**
   - Run the Streamlit app:
     ```
     streamlit run app.py
     ```
   - The app will open in your default web browser.

3. **Selecting a Song:**
   - Use the dropdown menu to select a song from the available options.

4. **Viewing Recommendations:**
   - After selecting a song, click the "Show Recommendation" button to view recommended songs based on similarity.

## Project Structure

- `app.py`: Main application script containing the Streamlit app.
- `requirements.txt`: List of dependencies required for the project.
- `df.pkl`: Pickle file containing preprocessed data about songs.
- `similarity.pkl`: Pickle file containing the precomputed similarity matrix.
- `README.md`: Documentation file containing project information (you're reading it!).

## Technologies Used

- Python
- Streamlit
- Spotipy
- Pandas
- Git

## Text Cleaning and Preprocessing

```python
import pandas as pd

# Load the dataset
df = pd.read_csv("spotify_millsongdata.csv")

# Sample the dataset
df = df.sample(3000)

# Clean the text data
df['text'] = df['text'].str.lower().replace(r'^\w\s', ' ').replace(r'\n', ' ', regex = True)

# Tokenization and stemming
import nltk
from nltk.stem.porter import PorterStemmer

# Initialize the PorterStemmer
stemmer = PorterStemmer()

# Tokenization function
def token(txt):
    tokens = nltk.word_tokenize(txt)
    # Apply stemming to each token
    stemmed_tokens = [stemmer.stem(w) for w in tokens]
    return " ".join(stemmed_tokens)

# Apply tokenization to the 'text' column
df['text'] = df['text'].apply(lambda x: token(x)).




2. **Running the App:**
   - Run the Streamlit app:
     ```
     streamlit run app.py
     ```
   - The app will open in your default web browser.

3. **Selecting a Song:**
   - Use the dropdown menu to select a song from the available options.

4. **Viewing Recommendations:**
   - After selecting a song, click the "Show Recommendation" button to view recommended songs based on similarity.

## Preview Image

![Music Recommendation image](https://i.ibb.co/sR187KH/Recommendation-System-cover.jpg)



## Acknowledgements
- Streamlit
- Spotipy
- Pandas
- NLTK


## License
- This project is licensed under the MIT License - see the LICENSE file for details.