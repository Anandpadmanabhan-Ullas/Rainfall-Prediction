# 🌧️ Rainfall Prediction Using Machine Learning

## 📌 Project Overview

This project uses Machine Learning to predict whether it will rain the following day based on historical Australian weather observations.

The system uses a **Random Forest Classifier** to learn patterns from weather data and predict the target variable `RainTomorrow`.

The project demonstrates the application of machine learning techniques to weather forecasting, including data preprocessing, model training, performance evaluation, and prediction.

## 🎯 Objectives

* Analyze historical weather data to identify patterns associated with rainfall.
* Preprocess the dataset to make it suitable for machine learning.
* Train a Random Forest classification model.
* Evaluate the model using standard classification metrics.
* Predict whether it will rain the following day based on weather observations.

## 📊 Dataset

**Dataset:** Australian Weather Dataset (`weatherAUS.csv`)

The dataset contains historical weather observations from various locations across Australia.

### Dataset Details

| Property                                     | Description           |
| -------------------------------------------- | --------------------- |
| Original dataset size                        | 145,460 rows          |
| Number of columns                            | 23                    |
| Records after removing missing target labels | 142,193               |
| Target variable                              | `RainTomorrow`        |
| Problem type                                 | Binary classification |

### Features

The dataset includes weather-related attributes such as:

* Temperature
* Humidity
* Rainfall
* Sunshine
* Atmospheric pressure
* Wind speed and direction
* Cloud observations
* Weather station location
* Date

The target variable, `RainTomorrow`, indicates whether rainfall occurred on the following day.

* `Yes` — Rain is expected.
* `No` — Rain is not expected.

**Dataset source:** The exact original download URL should be added here once verified against the source used for this project.

## 🧹 Data Preprocessing

The dataset was prepared before training the machine learning model.

The preprocessing workflow included:

1. Removing records with missing target labels.
2. Handling missing values in the input features.
3. Processing categorical features into a suitable numerical representation.
4. Preparing numerical features for model training.
5. Splitting the dataset into training and testing sets.

### Train-Test Split

The dataset was divided into training and testing subsets.

| Subset       | Number of records |
| ------------ | ----------------: |
| Training set |           113,754 |
| Testing set  |            28,439 |
| Total        |           142,193 |

The training set was used to develop the model, while the testing set was used to evaluate its performance on unseen data.

## 🤖 Machine Learning Algorithm

### Random Forest Classifier

The project uses a **Random Forest Classifier**, a supervised machine learning algorithm that combines multiple decision trees to make predictions.

Each decision tree learns patterns from the training data, and the model combines their predictions to produce the final classification.

### Why Random Forest?

* Can model nonlinear relationships between weather variables.
* Handles a mixture of numerical and categorical features when appropriately preprocessed.
* Combines multiple decision trees to improve predictive performance.
* Provides feature-importance estimates that help identify influential variables.
* Is suitable for binary classification problems.

### Model Workflow

1. Load the weather dataset.
2. Explore and preprocess the data.
3. Separate input features from the target variable.
4. Split the data into training and testing sets.
5. Train the Random Forest model.
6. Generate predictions on the testing set.
7. Evaluate the predictions using classification metrics.
8. Save the trained model for reuse.

## 📈 Model Evaluation

The model was evaluated using several classification metrics.

| Metric                     | Result |
| -------------------------- | -----: |
| Accuracy                   | 84.14% |
| Precision for Rain (`Yes`) | 63.67% |
| Recall for Rain (`Yes`)    | 68.08% |
| F1-score for Rain (`Yes`)  | 65.80% |
| ROC-AUC                    | 0.8833 |

### Understanding the Results

* **Accuracy:** Approximately 84.14% of the test predictions were correct.
* **Precision:** Of the observations predicted as rainy, approximately 63.67% were actually rainy.
* **Recall:** The model identified approximately 68.08% of the actual rainy observations.
* **F1-score:** Balances precision and recall for the rainy class.
* **ROC-AUC:** Measures the model's ability to distinguish between the two classes across different classification thresholds.

Accuracy alone does not fully describe performance because rainy and non-rainy observations are not equally distributed in the dataset.

These results are based on the recorded evaluation of this project and may vary if the data split, preprocessing, or model configuration changes.

## 🔍 Feature Importance

The trained Random Forest model identified the following features among its most influential predictors:

| Feature          | Importance |
| ---------------- | ---------: |
| Humidity at 3 PM |   0.171650 |
| Rainfall         |   0.071285 |
| Sunshine         |   0.070557 |
| Pressure at 3 PM |   0.057437 |
| Wind Gust Speed  |   0.053231 |

These values represent the model's feature-importance estimates. They indicate how the features contributed to the model's predictions, but they do not establish causation.

## 🛠️ Technologies Used

* **Python** — Main programming language
* **Jupyter Notebook** — Model development and experimentation
* **Pandas** — Data manipulation
* **NumPy** — Numerical operations
* **Scikit-learn** — Machine learning and model evaluation
* **Matplotlib / Seaborn** — Data visualization
* **Pickle** — Saving and loading the trained model
* **Gradio** — User interface, if included in the repository

## 📁 Project Structure

The repository may contain the following files:

```text
Rainfall-Prediction/
├── Rainfall_prediction_new.ipynb
├── weatherAUS.csv
├── rainfall_prediction_model.pkl
├── README.md
└── requirements.txt
```

**Note:** This is an illustrative structure. The actual repository contents should be reflected here, and any files that are not present should be removed from the list.

| File                            | Purpose                                                               |
| ------------------------------- | --------------------------------------------------------------------- |
| `Rainfall_prediction_new.ipynb` | Contains data analysis, preprocessing, model training, and evaluation |
| `weatherAUS.csv`                | Historical weather dataset                                            |
| `rainfall_prediction_model.pkl` | Serialized trained model, if included                                 |
| `README.md`                     | Project documentation                                                 |
| `requirements.txt`              | Python dependencies required to run the project                       |

## ⚙️ Installation and Usage

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_REPOSITORY_FOLDER>
```

Replace the placeholders with your actual GitHub repository URL and folder name.

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv .venv
```

Activate the environment.

**Windows:**

```bash
.venv\Scripts\activate
```

**Linux / macOS:**

```bash
source .venv/bin/activate
```

### 3. Install Dependencies

If the repository contains a `requirements.txt` file, run:

```bash
pip install -r requirements.txt
```

Otherwise, install the packages required by the notebook and interface.

### 4. Run the Jupyter Notebook

```bash
jupyter notebook Rainfall_prediction_new.ipynb
```

Execute the notebook cells in order to explore the dataset, preprocess the data, train the model, and review the evaluation results.

### 5. Run the Prediction Interface

If the repository includes a Gradio application, run its Python script using the appropriate filename.

For example:

```bash
python app.py
```

The command above assumes that the interface script is named `app.py`; use the actual filename in your repository.

## ⚠️ Limitations

* The model is trained on historical Australian weather observations and may not generalize well to other geographical regions.
* Weather conditions are complex and can change rapidly.
* The dataset contains missing values and an imbalance between rainy and non-rainy observations.
* Model performance depends on the quality of the input data and the preprocessing pipeline.
* Predictions should not be treated as a replacement for official meteorological forecasts.

## 🚀 Future Improvements

Potential improvements include:

* Evaluating the model on additional datasets and geographical regions.
* Experimenting with alternative classification algorithms.
* Improving recall for rainy observations.
* Tuning model hyperparameters.
* Adding more comprehensive error analysis.
* Deploying the prediction interface as a web application.
* Monitoring model performance on newer weather data.

## 👨‍💻 Author

Developed as a Machine Learning project to explore weather data analysis, classification, and rainfall prediction.

## 📄 License

Add an appropriate license if you intend to distribute this project publicly. Also verify the dataset's usage terms before redistributing the dataset itself.
