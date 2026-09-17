# Syntecxhub_-sentiment_analysis_tool.py# Sentiment Analysis using NLP and Machine Learning

A machine learning project that analyzes text and predicts whether the sentiment is **positive** or **negative**. The project uses **NLP preprocessing, TF-IDF feature extraction, and Logistic Regression** for classification. It also provides a simple **CLI interface** for real-time sentiment prediction.

## 📌 Project Overview

Sentiment analysis is a Natural Language Processing (NLP) task used to determine the emotional tone of text.

This project performs the following steps:

1. Loads labeled text data.
2. Cleans and preprocesses the text.
3. Converts text into numerical features using **TF-IDF**.
4. Trains a **Logistic Regression** classifier.
5. Evaluates the model using accuracy, precision, recall, and F1-score.
6. Saves the trained model and vectorizer.
7. Provides a command-line interface for predicting sentiment on new text.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas** – Data loading and manipulation
* **NumPy** – Numerical operations
* **NLTK** – Text preprocessing and stopwords
* **Scikit-learn** – Machine learning and evaluation
* **Joblib** – Saving and loading trained models
* **TF-IDF** – Text feature extraction
* **Logistic Regression** – Sentiment classification

---

## 📂 Project Structure

```text
sentiment-analysis-project/
│
├── data/
│   └── sentiment_data.csv
│
├── model/
│   ├── sentiment_model.pkl
│   └── vectorizer.pkl
│
├── sentiment_analysis.py
├── requirements.txt
└── README.md
```

### File Description

| File/Folder             | Description                     |
| ----------------------- | ------------------------------- |
| `data/`                 | Contains the sentiment dataset  |
| `sentiment_data.csv`    | Labeled text dataset            |
| `model/`                | Stores trained model files      |
| `sentiment_model.pkl`   | Saved Logistic Regression model |
| `vectorizer.pkl`        | Saved TF-IDF vectorizer         |
| `sentiment_analysis.py` | Main Python program             |
| `requirements.txt`      | Required Python libraries       |
| `README.md`             | Project documentation           |

---

## 📊 Dataset

The dataset contains two main columns:

```text
text,label
```

Example:

```csv
text,label
I love this movie,positive
This was the worst experience,negative
Amazing product quality,positive
Very disappointing service,negative
Absolutely fantastic,positive
Not worth the money,negative
```

The `text` column contains the input sentence, while the `label` column contains its sentiment.

> For meaningful model performance, use a sufficiently large and representative labeled dataset rather than only the small example dataset above.

---

## 🔄 Project Workflow

```text
Labeled Text Dataset
        ↓
Text Preprocessing
        ↓
Cleaned Text
        ↓
TF-IDF Feature Extraction
        ↓
Train/Test Split
        ↓
Logistic Regression
        ↓
Model Evaluation
        ↓
Save Model
        ↓
CLI Sentiment Prediction
```

---

## 🧹 Text Preprocessing

The project performs basic text preprocessing:

* Converts text to lowercase
* Removes punctuation and non-alphabetic characters
* Tokenizes text using whitespace splitting
* Removes English stopwords

Example:

```text
Original:
"I absolutely LOVE this product!"

After preprocessing:
"absolutely love product"
```

---

## 🔢 TF-IDF Feature Extraction

**TF-IDF (Term Frequency–Inverse Document Frequency)** converts text into numerical feature vectors.

It gives greater importance to words that are useful for distinguishing documents while reducing the importance of words that occur frequently across many documents.

The project uses:

```python
TfidfVectorizer(max_features=5000)
```

---

## 🤖 Machine Learning Model

The project uses **Logistic Regression** for binary sentiment classification.

```python
model = LogisticRegression()
model.fit(X_train, y_train)
```

The model learns patterns from the training data and predicts whether new text belongs to the positive or negative sentiment class.

---

## 📈 Model Evaluation

The trained model is evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

Example output:

```text
Model Evaluation:

Accuracy: 0.XX

Classification Report:

              precision    recall    f1-score

negative        0.XX       0.XX       0.XX
positive        0.XX       0.XX       0.XX
```

The actual scores depend on the dataset used for training and testing.

---

## 💾 Model Saving

After training, the model and TF-IDF vectorizer are saved using Joblib:

```python
joblib.dump(model, "model/sentiment_model.pkl")
joblib.dump(vectorizer, "model/vectorizer.pkl")
```

This allows the trained model to be reused without retraining every time.

---

## 💻 CLI Interface

The project provides a command-line interface where users can enter text and receive a predicted sentiment.

Example:

```text
Sentiment Analysis CLI
Type 'exit' to quit.

Enter text: I really enjoyed this product
Predicted Sentiment: positive

Enter text: This was a terrible experience
Predicted Sentiment: negative

Enter text: exit
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/sentiment-analysis-project.git
```

### 2. Navigate to the project

```bash
cd sentiment-analysis-project
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Run the Project

Run:

```bash
python sentiment_analysis.py
```

You will see:

```text
1. Train Model
2. Load Saved Model
```

### Option 1: Train Model

Choose:

```text
1
```

The program will:

* Load the dataset
* Preprocess the text
* Generate TF-IDF features
* Train the Logistic Regression model
* Evaluate the model
* Save the model
* Start the CLI

### Option 2: Load Existing Model

Choose:

```text
2
```

The previously saved model and vectorizer will be loaded and you can directly enter text for prediction.

---

## 🧪 Example Predictions

| Input                       | Expected Sentiment |
| --------------------------- | ------------------ |
| `I loved the product`       | Positive           |
| `The service was excellent` | Positive           |
| `This movie was amazing`    | Positive           |
| `I hated the experience`    | Negative           |
| `The product was terrible`  | Negative           |
| `                           |                    |
