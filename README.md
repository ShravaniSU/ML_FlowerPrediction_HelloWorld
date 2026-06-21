# 🚀 Hello-World MLOps

A production-oriented Machine Learning Operations (MLOps) project demonstrating the complete lifecycle of an ML model—from training and artifact generation to containerization, API serving, and automated CI pipelines.

This project showcases how modern ML systems are built, packaged, tested, and deployed using industry-standard engineering practices.

---

## 📌 Project Overview

The objective of this project is to demonstrate an end-to-end MLOps workflow using a lightweight machine learning model trained on the Iris dataset.

The pipeline includes:

* Model training and evaluation
* Artifact generation and versioning
* Command-line inference
* REST API serving with Flask
* Docker containerization
* Automated CI/CD using GitHub Actions
* Reproducible environments

This repository serves as a foundational template for production-grade machine learning systems.

---

## 🏗️ Architecture

```text
                ┌─────────────────┐
                │ Training Script │
                │   train.py      │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Trained Model   │
                │  model.pkl      │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Metrics Report  │
                │ metrics.json    │
                └────────┬────────┘
                         │
         ┌───────────────┼───────────────┐
         ▼                               ▼
┌─────────────────┐           ┌─────────────────┐
│ CLI Inference   │           │ Flask API       │
│ run_model.py    │           │ src/app.py      │
└────────┬────────┘           └────────┬────────┘
         │                             │
         ▼                             ▼
   Predictions                   REST Endpoint
                                  /predict

         └───────────────┬───────────────┘
                         ▼
                Docker Container
                         ▼
                GitHub Actions CI
```

---

## ✨ Features

### Machine Learning

* Trains a classification model on the Iris dataset
* Generates performance metrics automatically
* Saves serialized model artifacts

### Reproducibility

* Dependency management through requirements.txt
* Deterministic training workflow
* Portable execution across environments

### Inference

* Command-line prediction interface
* REST API endpoint for real-time inference

### Containerization

* Dockerized application
* Consistent runtime environment
* Easy deployment across platforms

### CI/CD Automation

* Automated training pipeline
* Artifact generation during builds
* GitHub Actions integration

---

## ⚙️ Installation

### Create Virtual Environment

```bash
python -m venv .venv
```

Linux/Mac:

```bash
source .venv/bin/activate
```

Windows:

```powershell
.venv\Scripts\activate
```

### Install Dependencies

```bash
pip install --upgrade pip setuptools wheel

pip install -r requirements.txt
```

---

## 🧠 Train the Model

Run the training pipeline:

```bash
python train.py
```

Expected output:

```text
artifacts/
├── model.pkl
└── metrics.json
```

### Generated Artifacts

| Artifact     | Description              |
| ------------ | ------------------------ |
| model.pkl    | Serialized trained model |
| metrics.json | Model evaluation metrics |

---

## 🔍 Run Predictions from CLI

Perform inference directly from the command line.

```bash
python run_model.py --input "[5.1,3.5,1.4,0.2]"
```

Example Output:

```json
{
  "prediction": 0
}
```

---

## 🌐 Start the Prediction API

Launch the Flask application:

```bash
python src/app.py
```

Server:

```text
http://127.0.0.1:5000
```

### Prediction Endpoint

**POST** `/predict`

Request:

```json
{
  "features": [5.1,3.5,1.4,0.2]
}
```

cURL Example:

```bash
curl -X POST \
"http://127.0.0.1:5000/predict" \
-H "Content-Type: application/json" \
-d '{"features":[5.1,3.5,1.4,0.2]}'
```

Response:

```json
{
  "prediction": 0
}
```

---

## 🐳 Docker Deployment

### Build Image

```bash
docker build -t hello-mlops .
```

### Run Container

```bash
docker run -p 5000:5000 hello-mlops
```

Verify:

```bash
curl http://localhost:5000
```

---

## 🔄 CI/CD Pipeline

GitHub Actions automatically executes:

1. Environment setup
2. Dependency installation
3. Model training
4. Artifact generation
5. Workflow validation

### CI Workflow

```text
Push / Pull Request
          │
          ▼
 GitHub Actions
          │
          ▼
 Install Dependencies
          │
          ▼
 Train Model
          │
          ▼
 Generate Artifacts
          │
          ▼
 Upload Results
```

---

## 📊 MLOps Practices Demonstrated

This project incorporates several core MLOps principles:

* Automated model training
* Artifact management
* Reproducible environments
* Containerized deployment
* Continuous Integration (CI)
* API-based model serving
* Infrastructure portability
* Version-controlled workflows

---

## 🎯 Why This Project Matters

Many machine learning projects stop at training a model inside a notebook.

This project demonstrates the engineering side of machine learning:

✅ Reproducible training

✅ Automated workflows

✅ Containerization

✅ Model serving APIs

✅ CI/CD integration

✅ Production deployment readiness

These capabilities are critical for MLOps Engineer, Machine Learning Engineer, DevOps Engineer, and Platform Engineer roles.

---

## 🚀 Future Enhancements

Potential production upgrades:

* MLflow for experiment tracking
* DVC for dataset and model versioning
* Kubernetes deployment
* Model monitoring and drift detection
* Prometheus & Grafana integration
* Automated retraining pipelines
* AWS SageMaker deployment
* Feature store integration

---

## 🛠️ Technology Stack

| Category         | Technology     |
| ---------------- | -------------- |
| Language         | Python         |
| ML Library       | Scikit-Learn   |
| API              | Flask          |
| Serialization    | Pickle         |
| Containerization | Docker         |
| CI/CD            | GitHub Actions |
| Environment      | Virtualenv     |
| Version Control  | Git            |

---

## 📜 License

This project is released under the MIT License.

---

## 👨‍💻 Author

**Shravani Shirish Urankar**

Full Stack Engineer | DevOps Engineer | Aspiring MLOps Engineer

* Portfolio: https://www.shravaniurankar.in
* GitHub: https://github.com/ShravaniSU
* LinkedIn: https://linkedin.com/in/shravaniurankar

If you found this project useful, consider giving it a ⭐ on GitHub.
