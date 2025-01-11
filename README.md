# Sentiment Analysis Web App

This project is a simple sentiment analysis web application built using Flask, Scikit-learn, and Natural Language Processing (NLP) techniques. The app analyzes customer reviews and predicts whether the sentiment is positive or negative.

## Features

- **Text Preprocessing:** Removes stopwords, converts text to lowercase, and applies stemming using NLTK.
- **Emoji Processing:** Converts emojis to text using the `emoji` library.
- **Sentiment Analysis:** Uses a Naive Bayes classifier (Multinomial Naive Bayes) for sentiment prediction.
- **Interactive Web Interface:** A simple, interactive web interface that allows users to input reviews and get instant sentiment analysis.

## Requirements

- Python 3.x
- Flask
- scikit-learn
- pandas
- nltk
- emoji

## Setup and Installation

### 1. Clone this repository:
```bash
git clone https://github.com/yourusername/sentiment-analysis-flask-app.git
cd sentiment-analysis-flask-app
```

### 2. Install dependencies:

Make sure you have `pip` installed, then run:
```bash
pip install -r requirements.txt
```

**requirements.txt**
```plaintext
Flask==2.0.1
scikit-learn==0.24.2
pandas==1.3.0
nltk==3.6.3
emoji==1.6.3
```

### 3. Prepare the Dataset
- Place your dataset (e.g., `Reviews.csv`) in the appropriate directory (e.g., `D:\\projects\\Reviews.csv` in the script). The dataset should have at least two columns: `Review` and `Liked` (1 for positive sentiment, 0 for negative sentiment).

### 4. Preprocess and Train the Model
- If you haven't already, run the model training code (included in the script) to train the Naive Bayes classifier and vectorizer.

```python
import pickle

# Save the vectorizer and model
with open('vectorizer.pkl', 'wb') as f:
    pickle.dump(vectorizer, f)

with open('model.pkl', 'wb') as f:
    pickle.dump(model, f)
```

These pickle files will be used in the Flask app.

### 5. Run the Flask App
After setting everything up, you can start the Flask app by running the following command:

```bash
python app.py
```

The Flask app will be hosted at `http://127.0.0.1:5000`. Open this URL in your web browser.

### 6. Using the Web App
- Open the app in your browser (`http://127.0.0.1:5000`).
- Write a review in the provided text area and click on "Analyze Sentiment."
- The app will display whether the sentiment is **Positive** or **Negative** based on the review.

## File Structure

```
sentiment-analysis-flask-app/
│
├── app.py                    # Flask app code
├── requirements.txt          # List of Python dependencies
├── Reviews.csv               # Sample review dataset
├── vectorizer.pkl            # Pickled TF-IDF vectorizer
├── model.pkl                 # Pickled Naive Bayes model
└── README.md                 # This README file
```

## Explanation of Code

### 1. **Preprocessing**
   - The text data is preprocessed by:
     - Converting text to lowercase.
     - Removing stopwords.
     - Tokenizing the text.
     - Applying stemming to reduce words to their root form.
     - Converting emojis to text using the `emoji` library.

### 2. **Training the Model**
   - The dataset is split into training and testing sets (80% for training, 20% for testing).
   - A `TfidfVectorizer` is used to transform the text into numerical features.
   - A `MultinomialNB` model (Naive Bayes classifier) is trained to classify the sentiment.

### 3. **Flask Web App**
   - The app has a simple interface for users to input their review text.
   - The app uses the trained model and vectorizer (loaded from pickle files) to predict sentiment.

## Contributing

If you'd like to contribute to this project, feel free to fork the repository, create a branch, and submit a pull request with your changes. Contributions, issues, and feature requests are always welcome!

## License

This project is open-source and available under the MIT License. See the [LICENSE](LICENSE) file for more details.
```

### How to Save:

1. Create a new text file and name it `README.md`.
2. Paste the content above into the file.
3. Save the file.

Now, you have a complete README file for your project!


