# Not Functional anymore, see NLP-with-deep-learning-sentiment-analysis

# Dabchy App Review Sentiment Analysis

## Project Overview

This project analyzes customer reviews for Dabchy, a Tunisian online clothing marketplace application. The goal is to understand customer sentiment and provide actionable insights to optimize user experience and improve customer loyalty. We follow the CRISP-DM (Cross-Industry Standard Process for Data Mining) methodology.

### Data Source

*   Google Play Store reviews were collected using the SerpAPI.

### Data Extraction

The following data fields were extracted:

*   `title` (Review Title)
*   `rating` (Star Rating)
*   `snippet` (Review Text)
*   `Likes` (Number of Likes)
*   `Date` (Review Date)

The extracted data is stored in the `app_reviews.csv` file.

### Initial Data Assessment

*   The initial dataset was imbalanced.
*   There were redundant data entries.
*   There was 2 empty comments.

### Data Cleaning
*   Redundant data and empty comments were removed.

### Data Augmentation (EDA)

To address data imbalance and improve model robustness, data augmentation techniques were employed based on this paper: [https://arxiv.org/abs/1901.11196](https://arxiv.org/abs/1901.11196)

The following methods were used:

1.  **SN: Synonym Replacement**
2.  **RS: Random Swap**
3.  **RI: Random Insertion**
4.  **GPT generated reviews**

### Post-Augmentation Data Assessment

*   No redundant data entries.
*   No empty values.
*   Most reviews were relatively short.

### Focus
The project focused solely on textual review content

### Text Preprocessing Steps:

1.  **Translation:** Translated all reviews to English.
2.  **Lowercasing:** Converted all text to lowercase.
3.  **Punctuation Removal:** Removed punctuation (except exclamation marks, question marks, colons, semicolons, and quotes).
4.  **Stop Word Removal:** Removed common stop words.
5.  **Rare Word Removal:** Removed rare words.
    *   Example words removed: 'plz', 'technical', 'shown', 'je', 'thx', 'published', 'notification', 'category', 'vend', 'already'.
6.  **Lemmatization:** Applied lemmatization to reduce words to their base form.
7.  **Emoticon Conversion:** Converted emoticons to their textual representation.

### Data Labeling

*   Reviews were labeled using TextBlob to determine sentiment scores.

### Sentiment Classification

*   Reviews were classified into two categories based on their sentiment scores:
    *   **Positive:** score > 0
    *   **Negative:** score < 0

### Models Used

Supervised machine learning models were used for sentiment classification:

*   Bag of Words
*   TF-IDF (Term Frequency-Inverse Document Frequency)

### Evaluation Metrics

*   The performance of the Bag of Words and TF-IDF models was compared.
