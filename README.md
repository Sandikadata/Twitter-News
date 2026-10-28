# Twitter News Financial Analysis

## Project Overview

This project analyzes financial news and Twitter-style text data using Python, Natural Language Processing (NLP), exploratory data analysis, sentiment visualization, machine learning, and topic modeling. It explores sentiment patterns in financial text and applies text-classification models to identify patterns in the dataset.

## Objectives

- Clean and preprocess financial text data.
- Explore the distribution of sentiment labels.
- Visualize frequently occurring words using word clouds.
- Convert text into numerical features using TF-IDF and Count Vectorization.
- Build and evaluate Logistic Regression and Multinomial Naive Bayes models.
- Discover recurring themes in financial text using Latent Dirichlet Allocation (LDA).
- Compare classification performance using accuracy, classification reports, and confusion matrices.

## Dataset

The notebook uses separate training and validation datasets.

| Dataset | Initial records | Columns |
|---|---:|---:|
| Training data | 16,990 | 5 |
| Validation data | 4,117 | 5 |

The datasets contain the following columns:

- `text`: Original financial news text.
- `label`: Numeric classification label.
- `sentiment_score`: Numeric sentiment score.
- `sentiment`: Sentiment category supplied with the dataset.
- `clean_text`: Preprocessed text used for analysis and modeling.

**Note:** The notebook loads `train_data.csv` and `valid_data.csv` from Google Drive. You will need access to these files to reproduce the analysis.

## Technologies Used

- **Python**
- **Pandas** — data manipulation and analysis
- **Regular Expressions (re)** — text cleaning
- **Matplotlib and Seaborn** — visualizations
- **WordCloud** — word-frequency visualization
- **Scikit-learn** — text vectorization, machine learning, evaluation, and topic modeling
- **Google Colab** — notebook environment

## Project Workflow

### 1. Data Loading and Inspection
- Load the training and validation datasets.
- Inspect dataset dimensions, data types, and missing values.
- Explore sample records and numerical summaries.

### 2. Text Preprocessing
- Convert text to lowercase.
- Remove URLs and selected social-media symbols.
- Remove punctuation and non-alphabetic characters.
- Create cleaned text in the `clean_text` column.

### 3. Exploratory Data Analysis
- Examine sentiment distribution.
- Visualize sentiment counts.
- Create word clouds to explore common terms in the financial text.

### 4. Text Vectorization
Two approaches are used to represent text numerically:

- **TF-IDF Vectorization**
- **Count Vectorization**

Both vectorizers use English stop-word removal and a maximum vocabulary size of 5,000 features.

### 5. Machine Learning
The notebook trains and evaluates:

- Logistic Regression
- Multinomial Naive Bayes with TF-IDF features
- Multinomial Naive Bayes with Count Vectorization

Evaluation includes accuracy, precision, recall, F1-score, classification reports, and confusion matrices.

### 6. Topic Modeling
Latent Dirichlet Allocation (LDA) is used to identify five groups of frequently associated terms in the financial text.

The discovered themes include:
- Stock markets, investors, and trading
- Company announcements and earnings
- Financial results and dividends
- Interest rates, inflation, oil, and gas
- Markets, business, and investment activity

## Results

The recorded notebook outputs show the following accuracy scores:

| Model | Accuracy |
|---|---:|
| Logistic Regression with TF-IDF | 77.82% |
| Multinomial Naive Bayes with TF-IDF | 71.12% |

Logistic Regression achieved the higher recorded accuracy of these two models.

The notebook also generates classification reports and confusion matrices to examine performance across individual numeric labels.

**Important modeling note:** The current code trains the classifiers using the numeric `label` column, which contains multiple label values. Therefore, the reported accuracy measures prediction of those numeric labels; it should not automatically be interpreted as sentiment-classification accuracy. To evaluate sentiment classification specifically, the target variable should be the `sentiment` column, with the target encoding and evaluation updated accordingly.

## How to Run the Project

1. Download or clone this repository.
2. Open `Twitter_News_Financial_Analysis.ipynb` in Google Colab or Jupyter Notebook.
3. Install the required Python libraries if they are not already available.
4. Make the training and validation CSV files accessible.
5. Update the CSV file paths in the notebook to match your environment.
6. Run the notebook cells in sequence to reproduce the analysis and model evaluation.

## Skills Demonstrated

- Data cleaning and preprocessing
- Exploratory data analysis (EDA)
- Natural Language Processing (NLP)
- Text feature engineering
- Machine learning
- Model evaluation
- Topic modeling
- Data visualization
- Financial text analytics

## Conclusion

This project demonstrates an end-to-end text analytics workflow for financial news data, from preprocessing and exploratory analysis to machine learning and topic discovery. It provides a foundation for further work on financial sentiment classification and analysis of market-related news.

## Future Improvements

- Train and evaluate a dedicated sentiment classifier using the `sentiment` column.
- Investigate class imbalance and improve performance on underrepresented labels.
- Add model comparisons using macro-F1 and weighted-F1 scores.
- Improve preprocessing and validate the topic-modeling results.
- Experiment with advanced NLP models for financial text.


