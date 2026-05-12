# Movie_Suggester

A content-based movie recommendation system built with Python, Flask, and Natural Language Processing (NLP).

The application analyzes movie descriptions, genres, and keywords to recommend films similar to the one selected by the user. The project uses data from TMDB and applies TF-IDF vectorization with cosine similarity to generate recommendations.

---

## Live Demo

**Application:**  
https://sugmov2.onrender.com/

**GitHub Repository:**  
https://github.com/YauheniBudzko/Movie_Suggester

---

## Project Overview

Movie Suggester is a machine learning project focused on building a movie recommendation engine using a **content-based filtering approach**.

Instead of relying on user ratings or collaborative filtering, the system compares movie metadata such as:

- Overview
- Genres
- Keywords

The recommendation engine processes textual data, transforms it into numerical vectors using TF-IDF vectorization, and calculates similarity scores between movies using cosine similarity. :contentReference[oaicite:0]{index=0}

---

## Features

- Search movies by title
- Get top recommended similar movies
- Content-based recommendation algorithm
- NLP preprocessing and stemming
- TF-IDF vectorization
- Cosine similarity matrix
- Flask web application
- Deployed on Render

---

## Tech Stack

### Backend
- Python
- Flask
- Scikit-learn
- Pandas
- NumPy
- NLTK

### Machine Learning / NLP
- TF-IDF Vectorizer
- Cosine Similarity
- Porter Stemmer
- Text preprocessing and tokenization

### Frontend
- HTML
- CSS
- JavaScript

### Deployment
- Render
- Git LFS

---

## Dataset

The project uses the **TMDB Movies Dataset** from Kaggle.  
Selected columns used for recommendation generation:

- `id`
- `title`
- `overview`
- `genres`
- `keywords`

The remaining columns were excluded because they were not essential for the content-based recommendation model. :contentReference[oaicite:1]{index=1}

---

## How the Recommendation System Works

### 1. Data Loading

The dataset is downloaded from Kaggle using the Kaggle API and loaded into a Pandas DataFrame. :contentReference[oaicite:2]{index=2}

### 2. Data Preprocessing

The following preprocessing steps are applied:

- Removing unnecessary columns
- Removing missing values
- Removing duplicates
- Limiting the dataset to 5000 movies due to memory and deployment limitations
- Tokenization of text fields
- Combining overview, genres, and keywords into one feature column :contentReference[oaicite:3]{index=3}

### 3. NLP Processing

The project uses stemming with NLTK's PorterStemmer to normalize words with the same root, improving recommendation quality. :contentReference[oaicite:4]{index=4}

Example:
- `love`
- `loving`
- `loved`

All become a common root representation.

---

### 4. Vectorization

The processed text data is transformed using TF-IDF vectorization.  
Each movie becomes a numerical vector representation. :contentReference[oaicite:5]{index=5}

---

### 5. Similarity Matrix

Cosine similarity is calculated between all movie vectors, creating a similarity matrix that allows the system to identify movies with related content. :contentReference[oaicite:6]{index=6}

---

### 6. Recommendation Function

The recommendation algorithm:

1. Finds the selected movie index
2. Retrieves similarity scores
3. Sorts movies by similarity
4. Returns the top matching recommendations :contentReference[oaicite:7]{index=7}

Example recommendation:
- Input: `Back to the Future`
- Output:
  - Back to the Future Part II
  - Back to the Future Part III
  - Tomorrowland
  - Meet the Robinsons

:contentReference[oaicite:8]{index=8}

---

## Project Structure

```bash
Movie Suggester/
│
├── static/
│   └── style.css
│
├── templates/
│   └── index.html
│
├── app.py
├── movies.pkl
├── similarity.pkl
├── requirements.txt
├── .render-build.sh
├── .gitattributes
└── README.md
```

## Important Files
| File               | Description                           |
| ------------------ | ------------------------------------- |
| `app.py`           | Flask application                     |
| `movies.pkl`       | Saved movie dataframe                 |
| `similarity.pkl`   | Cosine similarity matrix              |
| `style.css`        | UI styling                            |
| `index.html`       | Frontend page                         |
| `.render-build.sh` | Render deployment script              |
| `.gitattributes`   | Git LFS configuration for large files |

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YauheniBudzko/Movie_Suggester.git
cd Movie_Suggester
```

### 2. Create a virtual environment
```bash
python -m venv venv
```

### 3. Activate the environment
- Windows
```bash
venv\Scripts\activate
```

- MacOS/Linux
```bash
source venv/bin/activate
```

### 4. Install dependencies
```bash
pip install -r requirements.txt
```

### 5. Run the application
```bash
python app.py
```

## Deployment
The application is deployed on Render using a custom build script.
Git Large File Storage (Git LFS) is used to store large model files such as `similarity.pkl`.

## Author
Machine Learning & Full-Stack Project
Created by Yauheni Budzko


