# Movie_reccomendation_system

### Overview

This project implements a movie recommendation system that uses machine learning techniques to suggest films based on user preferences. By analyzing metadata from The Movie Database (TMDb), it aims to provide users with personalized movie suggestions.

### Features

- Data Processing: Extracts and cleans relevant features from TMDb datasets, including:
  - Genres
  - Keywords
  - Cast and crew information
- Content-Based Filtering: Uses cosine similarity to find and recommend movies with similar attributes.
- Interactive Web App: Built with Streamlit, allowing a user-friendly interface for selecting movies and viewing recommendations.
- Dynamic Movie Posters: Integrates TMDb API to fetch and display movie posters, enhancing user experience.

### Technical Details

- Data Source: The project uses two main datasets from TMDb:
  - `tmdb_5000_movies.csv`: Contains movie metadata.
  - `tmdb_5000_credits.csv`: Contains cast and crew information.
- Data Processing Libraries: Utilizes `pandas` for data manipulation and `numpy` for numerical operations.
- Machine Learning: Implements `scikit-learn` for computing cosine similarity.
- Web Framework: Built on `Streamlit`, allowing for rapid development of web applications.

### Installation

To set up the project locally, follow these steps:

1. Clone the Repository:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. Install Dependencies:
   Ensure you have Python installed, then run:
   ```bash
   pip install -r requirements.txt
   ```

### Usage

1. Load Data: 
   The application loads the processed movie dataset and similarity matrix from pickle files:
   ```python
   movies = pd.read_pickle(open('movie_list.pkl','rb'))
   similarity = pickle.load(open('similarity.pkl','rb'))
   ```

2. Run the Streamlit App:
   Launch the app using:
   ```bash
   streamlit run app.py
   ```
   Navigate to the displayed local URL in your web browser.

3. Select a Movie:
   Use the dropdown menu to choose a movie. Upon clicking the "Show Recommendation" button, the app displays a list of similar films and their posters.

### Example Recommendations

For instance, selecting "Inception" might yield recommendations like:
- Interstellar
- The Matrix
- Shutter Iland
- Memento
- The Prestige

### Project Structure

```
/movie-recommender
│
├── app.py                   # Main Streamlit application
├── movie_list.pkl           # Pickled movie dataset
├── similarity.pkl           # Pickled similarity matrix
├── requirements.txt         # List of dependencies
├── README.md                # Project documentation
└── LICENSE                  # License information
```

### Acknowledgements

- The Movie Database (TMDb): For providing the datasets used in this project.
- Scikit-learn: For machine learning functionalities, particularly cosine similarity.
- Streamlit: For enabling the creation of the web application interface.

### Future Enhancements

- User Rating Integration: Implement user ratings to refine recommendations further.
- Expanded Datasets: Utilize additional datasets to capture more movie attributes (e.g., reviews, box office performance).
- Collaborative Filtering: Explore collaborative filtering methods to recommend movies based on user behavior patterns.
- Enhanced UI/UX: Improve the user interface with additional features like search filters, movie trailers, and detailed information.
- Mobile Compatibility: Optimize the web app for mobile devices to enhance accessibility.
