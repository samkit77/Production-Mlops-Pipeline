# Production-MLops-Pipeline

An end-to-end **sentiment analysis** project built with **Flask, MLflow, Docker, AWS, EKS, and GitHub Actions**. The project covers the complete machine learning lifecycle: data ingestion, preprocessing, feature engineering, model training, evaluation, model registry, API serving, CI/CD, containerization, and deployment.

---

## Project Highlights

- **Text classification** for positive/negative sentiment
- **MLflow** for experiment tracking and model registry
- **Flask web app** for live predictions
- **GitHub Actions CI/CD** for automated testing, build, and deployment
- **AWS S3** for cloud storage
- **AWS ECR + EKS** for Docker image storage and Kubernetes deployment

---

## Tech Stack

**ML / NLP:** scikit-learn, NLTK, NumPy, Pandas  
**Experiment Tracking:** MLflow  
**Web App:** Flask  
**Containerization:** Docker  
**Cloud / DevOps:** AWS S3, ECR, EKS, GitHub Actions  

---

## Repository Structure
``` text.
├── .github/workflows/ci.yaml
├── params.yaml
├── requirements.txt
├── Dockerfile
├── flask_app/
│ ├── app.py
│ └── templates/
│ └── index.html
├── src/
│ ├── logger.py
│ ├── connections/
│ │ └── s3_connection.py
│ ├── data/
│ │ ├── data_ingestion.py
│ │ └── data_preprocessing.py
│ ├── features/
│ │ └── feature_engineering.py
│ └── model/
│ ├── model_building.py
│ ├── model_evaluation.py
│ └── register_model.py
├── tests/
├── scripts/
├── models/
├── data/
├── reports/
└── logs/
```

---

# Workflow Overview

## 1. Data Ingestion

- Load dataset from CSV or S3
- Filter relevant sentiment labels
- Split into train and test sets

---

## 2. Data Preprocessing

- Lowercasing
- URL removal
- Number removal
- Punctuation removal
- Stop word removal
- Lemmatization

---

## 3. Feature Engineering

- Convert text into **Bag of Words** features using `CountVectorizer`
- Save fitted vectorizer for inference

---

## 4. Model Training

- Train **Logistic Regression** on processed features
- Save trained model as `model.pkl`

---

## 5. Model Evaluation

Evaluate model performance using:

- Accuracy
- Precision
- Recall

Save evaluation metrics and experiment information.

---


## 6. Flask Inference App

- Accept user text input
- Apply the same preprocessing pipeline
- Transform text using the saved vectorizer
- Generate sentiment predictions using the registered model

---

## 7. CI/CD Workflow

The GitHub Actions pipeline performs:

- Code checkout
- Python environment setup
- Dependency installation
- Unit testing
- Model validation
- Flask application testing
- Docker image build
- AWS ECR authentication
- Push Docker image to AWS ECR
- Deploy application to AWS EKS

---

# Deployment Architecture

The application deployment flow:


Developer
|
|
GitHub Repository
|
|
GitHub Actions CI/CD
|
|
Docker Build
|
|
AWS ECR
|
|
AWS EKS Kubernetes Cluster
|
|
Flask ML Application


---

# Model Lifecycle


Data
|
|
Preprocessing
|
|
Feature Engineering
|
|
Model Training
|
|
Evaluation
|
|
MLflow Tracking
|
|
Model Registry
|
|
Production Deployment
|
|
Flask API Prediction


---

# Key Features

- End-to-end ML pipeline
- Experiment tracking with MLflow
- Model versioning and registry
- Automated CI/CD pipeline
- Docker-based deployment
- Kubernetes-based production deployment
- AWS cloud integration