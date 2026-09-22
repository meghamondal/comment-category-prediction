# Comment Category Prediction

A multiclass machine-learning project for predicting the category of online comments using text, engagement signals, categorical features, and time-related information.

## Project Overview

This project was developed for the **Comment Category Prediction Challenge** on Kaggle.

The goal is to predict the `label` assigned to each comment. The project includes exploratory data analysis, feature engineering, data preprocessing, model training, model comparison, evaluation, and prediction generation.

## Dataset

The dataset contains training and test data for comment category prediction.

- `train.csv` — Training data containing the target variable `label`
- `test.csv` — Test data used for generating predictions
- `sample_submission.csv` — Sample submission format

### Main Features

- `comment` — Text content of the comment
- `created_date` — Date and time information
- `post_id` — Associated post identifier
- `upvote`, `downvote` — Engagement features
- `if_1`, `if_2` — Additional numeric features
- `emoticon_1`, `emoticon_2`, `emoticon_3` — Emoticon indicators
- `race`, `religion`, `gender`, `disability` — Additional categorical/indicator features
- `label` — Target variable

The target contains four classes and is imbalanced.

> The original dataset is not included in this repository. It is loaded through the Kaggle environment.

## Features & Feature Engineering

The project uses a combination of text and structured features.

### Text Features

The `comment` column is processed and transformed using **TF-IDF vectorization**.

Additional text-based features are also created, including:

- Comment length
- Question mark count
- Exclamation mark count
- Other text-related statistics

### Numerical Features

The model uses features such as:

- Upvotes
- Downvotes
- Internal numeric features
- Text-derived numerical features

### Categorical Features

The project uses:

- Emoticon indicators
- `race`
- `religion`
- `gender`
- `disability`

Categorical features are processed using appropriate encoding techniques.

### Date Features

The `created_date` column is converted into useful time-related features such as:

- Day
- Hour
- Month
- Year

## Data Preprocessing

The preprocessing workflow includes:

1. Handling missing values
2. Cleaning and processing comment text
3. Extracting text-based features
4. Extracting date and time features
5. Encoding categorical features
6. Scaling or transforming numerical features where required
7. Applying TF-IDF to comment text
8. Combining text and structured features for model training

## Models

Several machine-learning models were explored and compared:

- Multinomial Naive Bayes
- Logistic Regression
- Linear Support Vector Machine
- SGD-based classifier
- LightGBM Classifier

Models were evaluated using validation data, with **Macro F1 Score** as the primary metric.

## Evaluation & Results

The primary evaluation metric is **Macro F1 Score**.

Macro F1 calculates the F1 score for each class independently and then averages the scores, giving equal importance to each class.

Based on the model comparison in the notebook, **LightGBM** provided the strongest validation performance among the evaluated approaches.

The notebook contains the complete validation results and model comparison.

## Final Model

The final approach uses a **LightGBM Classifier** for generating predictions.

The notebook contains the model configuration, training process, validation results, and final prediction workflow.

## Kaggle Notebook Execution

The project was developed and executed using a **Kaggle Notebook**.

To reproduce the project:

1. Open a Kaggle Notebook.
2. Attach the required competition dataset.
3. Upload or open `kaggle-notebook.ipynb`.
4. Make sure the required input files are available.
5. Run the notebook cells sequentially.
6. Review the exploratory analysis and validation results.
7. Run the final prediction cells to generate the submission file.

## Setup & Usage

### Install Dependencies

For local execution, install the libraries used in the notebook:

```bash
pip install pandas numpy scikit-learn lightgbm matplotlib seaborn jupyter
```

### Run the Notebook

```bash
jupyter notebook
```

Then open:

```text
kaggle-notebook.ipynb
```

The competition dataset must be obtained separately and the input paths may need to be updated when running outside Kaggle.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- LightGBM
- Matplotlib
- Seaborn
- Jupyter Notebook
- Kaggle

## Repository Structure

```text
comment-category-ml-project/
│
├── README.md
└── kaggle-notebook.ipynb
```

## Key Takeaways

This project provided practical experience with:

- Exploratory Data Analysis
- Text preprocessing
- TF-IDF feature extraction
- Feature engineering
- Numerical and categorical data processing
- Multiclass classification
- Model comparison
- LightGBM
- Macro F1 evaluation
- Kaggle competition workflow
- Generating predictions and submissions

## Reproducibility

- The competition dataset is not included in the repository.
- The notebook is designed primarily for the Kaggle environment.
- Results may vary depending on the data split, library versions, and execution environment.
- The notebook should be run sequentially to reproduce the complete workflow.
