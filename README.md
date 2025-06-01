
# 🎬 Movie Recommender Prototype with XAI

This is a hybrid movie recommendation system built with **Streamlit** and powered by **MovieLens** data. It allows users to receive personalized movie suggestions based on natural language input and past movie ratings. It also supports user feedback and explainable AI (XAI) techniques like SHAP.

---

## 📂 Project Structure

```
movie_recommender/
├── app.py                    # Main Streamlit application
├── data_processor.py         # File to load and manage the datasets
├── stats_data.py             # File to get the data to populate the graphs from the main application
├── extract_descriptions.py   # Script to enrich MovieLens data with Wikipedia descriptions
├── dataset/                  # Folder containing datasets (movies.csv, ratings.csv, tags.csv, etc.)
├── requirements.txt          # Python dependencies
```

---

## 🚀 Features

- 🎯 Hybrid recommendations (text query + user profile + rating score)
- 💬 Natural language input to describe what you want to watch
- ⭐ Feedback system (0 to 5 stars) to improve the model
- 📖 Description and intro for each movie (scraped from Wikipedia)
- 📊 Explainable AI (XAI)
- 📄 Pagination to navigate large recommendation lists

---

## ⚙️ Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/iwhizerd/Movie_recomendator.git
cd Movie_recomendator
```

### 2. Install dependencies

Use a virtual environment and install the requirements:

```bash
pip install -r requirements.txt
```

> Requirements include: `streamlit`, `pandas`, `scikit-learn`, `xgboost`, `shap`, `SPARQLWrapper`, `beautifulsoup4`, etc.

---

### 3. Prepare the data

Place your MovieLens dataset files inside the `archive/` folder. For example:

```
dataset/
├── feedback.csv
├── genome_scores.csv
├── genome_tags.csv
├── link.csv
├── movie.csv
├── movies_with_genres_and_intro.csv
├── netflix_titles.csv
├── rating.csv
├── tag.csv
└── users.csv
```

You can download them from: https://drive.google.com/file/d/1Dp94b4369uF6pa3RRgpw09YgxPVoZEZQ/view?usp=drive_link

---

### 4. Enrich movie data with Wikipedia descriptions (optional but recommended)

Run the enrichment script to attach descriptions and intro text from Wikipedia:

```bash
python extract_descriptions.py
```

This will create `movies_with_wikipedia_intro.csv` containing:
- movieId
- clean title
- release year
- short description
- Wikipedia URL
- intro paragraph

---


### 5. Launch the Streamlit App

To launch the main dashboard with full explainability features (including score breakdowns, weight sliders, genre profiles, and Wikipedia enrichment), run:

```bash
streamlit run app.py
```

#### Available Streamlit interfaces

- **`app.py`** — Full-featured dashboard with explainability tools for advanced users. Includes pie chart breakdowns, genre-based user profiles, Wikipedia-based descriptions, and dynamic weight sliders for recommendation components.
- **`user.py`** — Simplified version of the app focused on casual users. It provides a lightweight interface with basic recommendation and feedback functionality, hiding most explainability elements.
- **`prototype.py`** — Initial development prototype used to test and validate core recommendation logic and explanation rendering.

Each interface is self-contained and can be launched with the same `streamlit run` command by replacing the filename as needed.


## 📄 License

MIT – feel free to use and adapt for educational or research purposes.
