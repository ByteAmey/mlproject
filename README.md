## End to End Machine Learning Project

# 🎓 Student Performance Prediction – End to End ML Project

An end-to-end machine learning project that predicts a student's **math score** from demographic and academic features. It covers the full lifecycle: exploratory data analysis, modular training pipelines, model selection, and a Flask web app that serves predictions through a simple form.

---

## 📌 Problem Statement

Understand how a student's performance in exams is affected by variables such as gender, ethnicity, parental level of education, lunch type, and test preparation course, and build a model that predicts the **math score** from those inputs.

## 🧾 Dataset

Student Performance dataset (commonly known as *StudentsPerformance.csv*) with 1,000 rows and the following columns:

| Column | Type | Description |
|---|---|---|
| `gender` | Categorical | Student's gender |
| `race_ethnicity` | Categorical | Ethnic group (Group A–E) |
| `parental_level_of_education` | Categorical | Highest education level of parents |
| `lunch` | Categorical | Standard or free/reduced lunch |
| `test_preparation_course` | Categorical | Completed or none |
| `reading_score` | Numerical | Score in reading |
| `writing_score` | Numerical | Score in writing |
| `math_score` | Numerical | **Target variable** |

## 🛠️ Tech Stack

- **Language:** Python 3
- **Data & ML:** Pandas, NumPy, Scikit-learn, CatBoost, XGBoost
- **Visualization:** Matplotlib, Seaborn
- **Web app:** Flask, HTML templates
- **Utilities:** dill (object serialization), setuptools (packaging)

## 🔄 Project Workflow

1. **Data Ingestion** – Read the raw dataset and split it into train and test sets.
2. **Data Transformation** – Build a preprocessing pipeline: imputation, one-hot encoding for categorical features, and standard scaling for numerical features.
3. **Model Training** – Train and compare multiple regression models (e.g. Linear Regression, Decision Tree, Random Forest, Gradient Boosting, XGBoost, CatBoost, AdaBoost) with hyperparameter tuning, then select the best one by R² score.
4. **Model Persistence** – Save the preprocessor and best model as pickle files in `artifacts/`.
5. **Prediction Pipeline** – Load the saved objects and generate predictions for new inputs.
6. **Web App** – A Flask app exposes a form where users enter student details and get the predicted math score.

## 📁 Project Structure

```
├── .ebextensions/        # AWS Elastic Beanstalk configuration
├── artifacts/            # Saved data splits, preprocessor and trained model
├── logs/                 # Application logs
├── notebook/             # EDA and model training experiments
├── src/
│   ├── components/       # Data ingestion, transformation, model trainer
│   ├── pipeline/         # Train and predict pipelines (CustomData, PredictPipeline)
│   ├── exception.py      # Custom exception handling
│   ├── logger.py         # Logging setup
│   └── utils.py          # Helper functions (save/load objects, evaluate models)
├── templates/            # HTML templates (index.html, home.html)
├── app.py                # Flask app (local development)
├── application.py        # Flask app entry point (Elastic Beanstalk naming)
├── requirements.txt      # Python dependencies
├── setup.py              # Package setup
└── README.md
```

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS / Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Train the model

Run the data ingestion script, which triggers transformation and training and saves the artifacts:

```bash
python src/components/data_ingestion.py
```

### 5. Run the web app

```bash
python application.py
```

Open your browser at `http://127.0.0.1:5000/` and go to `/predictdata` to try out the predictor.

## 🖥️ Usage

1. Open the **/predictdata** page.
2. Fill in the form: gender, race/ethnicity, parental level of education, lunch type, test preparation course, reading score, and writing score.
3. Submit the form to see the predicted **math score**.

## 📊 Results

Add your final results here, for example:

| Model | R² Score |
|---|---|
| Best model | _your score_ |

> Replace this table with the actual metrics from your model trainer output.

## 🔮 Future Improvements

- Deploy the app on AWS Elastic Beanstalk, Render, or Docker
- Add a CI/CD pipeline with GitHub Actions
- Add input validation and better error handling in the web form
- Experiment with feature engineering and additional models
- Track experiments with MLflow

## 👤 Author

**Amey**
📧 kambleamey0612@gmail.com

---

⭐ If you found this project useful, consider giving the repo a star!
