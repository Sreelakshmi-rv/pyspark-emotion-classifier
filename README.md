# Text Emotion Classification with PySpark 

This project demonstrates a complete machine learning pipeline for text classification using Apache Spark's MLlib. The goal is to classify a piece of text into one of several emotion categories (e.g., joy, sadness, anger). The entire workflow, from data cleaning to model evaluation, is encapsulated within a Spark ML Pipeline.

---

##  Project Workflow

1.  **Data Loading:** The application starts by creating a `SparkSession` and loading the `emotions.csv` dataset.

2.  **Preprocessing:** It selects the essential `text` and `label` columns and removes any rows with null values to ensure data quality.

3.  **Feature Engineering:** A multi-step process converts the raw text into numerical features suitable for machine learning:
    * **Tokenizer**: Splits sentences into individual words.
    * **StopWordsRemover**: Filters out common, non-informative words (e.g., 'the', 'a', 'is').
    * **HashingTF & IDF**: Converts the filtered words into numerical vectors using the TF-IDF (Term Frequency-Inverse Document Frequency) technique.

4.  **Model Training:** A **Logistic Regression** classifier is trained on the processed data.

5.  **Pipelining:** All the above steps are chained together into a single `Pipeline` for an efficient and reproducible workflow.

6.  **Evaluation:** The trained model is used to make predictions on a held-out test set, and its final accuracy is calculated and displayed.

---

##  Tech Stack

* **Python**
* **Apache Spark** (via **PySpark**)
* **Spark MLlib** for machine learning components

---

##  Dataset

This project requires a CSV file named `emotions.csv` located in the same directory as the script. The CSV must contain at least two columns:
* `text`: The text content to be classified.
* `label`: The corresponding emotion category.

**Note:** The dataset is not included in this repository and must be acquired separately.
