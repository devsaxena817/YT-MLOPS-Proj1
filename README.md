

---
# 🚗 Vehicle MLOps Project

![Python](https://img.shields.io/badge/Python-3.10-blue) 
![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green)
![AWS](https://img.shields.io/badge/AWS-Cloud-orange)
![Docker](https://img.shields.io/badge/Docker-Container-blue)
![GitHub Actions](https://img.shields.io/badge/CI--CD-GitHubActions-purple)

> **End-to-end MLOps pipeline** for vehicle data: from ingestion to deployment with cloud integration and CI/CD automation.

---

## 🌟 Project Overview

This project demonstrates a **production-ready MLOps pipeline** with:

- Data ingestion from **MongoDB Atlas**
- Data validation and transformation
- Model training, evaluation, and deployment
- Integration with **AWS S3** for model registry
- Deployment on **EC2** with Docker
- Automated **CI/CD pipeline** using GitHub Actions
- Modular, maintainable, and scalable architecture

The project emphasizes **best practices in MLOps**, **logging**, **exception handling**, and **clean code structure**.



## 🏗️ Setup & Installation

### 1. Project Template
```bash
python template.py
````

### 2. Local Package Management

* Configure `setup.py` and `pyproject.toml` for local imports
* Check `crashcourse.txt` for details

### 3. Virtual Environment & Dependencies

```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt
pip list  # verify installation
```



## 🗄️ MongoDB Atlas Setup

1. Sign up at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a new project → cluster (M0) → DB user → allow IP: `0.0.0.0/0`
3. Get Python connection string and set as environment variable:

```bash
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster0.mongodb.net"
```

4. Test in `notebooks/mongoDB_demo.ipynb` (dataset upload and verification)

---

## 📝 Logging & Exception Handling

* Centralized **logger** in `logger.py`
* Custom **exceptions** in `exception.py`
* Modular design for maintainability

---

## 📊 Data Pipeline Components

### Data Ingestion

* Fetch data from MongoDB → transform → store in DataFrame
* Config and artifacts: `entity/config_entity.py` & `entity/artifact_entity.py`
* Pipeline: `components/data_ingestion.py` → run `demo.py`

### Data Validation & Transformation

* Validate data → transform features → save processed data
* Estimators implemented in `entity/estimator.py`

### Model Training & Evaluation

* Training pipeline: `components/model_trainer.py`
* Evaluate performance → threshold defined in `constants/__init__.py`
* S3 integration for model storage: `src/aws_storage/s3_estimator.py`

---

## ☁️ AWS Integration

* **S3 bucket**: `my-model-mlopsproj`
* Environment variables:

```bash
export AWS_ACCESS_KEY_ID="..."
export AWS_SECRET_ACCESS_KEY="..."
export AWS_DEFAULT_REGION="us-east-1"
```

* Use `src/configuration/aws_connection.py` to manage S3 operations
* Push/pull models programmatically for reproducibility

---

## 🚀 Deployment & CI/CD

* **Dockerized** application with `Dockerfile` & `.dockerignore`
* **CI/CD** via GitHub Actions (`.github/workflows/aws.yaml`)
* EC2 deployment on port `5080`
* Trigger training and inference via `/training` and `/predict` routes
* Self-hosted GitHub Actions runner for continuous integration

```bash
http://<EC2_PUBLIC_IP>:5080
```

---

## 📁 Project Structure

```
Vehicle_MLOps/
├── artifact/
├── src/
│   ├── components/
│   ├── configuration/
│   ├── data_access/
│   ├── entity/
│   ├── aws_storage/
│   └── app.py
├── notebooks/
│   ├── mongoDB_demo.ipynb
│   └── eda_feature_engg.ipynb
├── requirements.txt
├── Dockerfile
├── .github/workflows/aws.yaml
├── setup.py
└── pyproject.toml
```

---

## 🏆 Key Learning Outcomes

* Full **MLOps lifecycle implementation**
* Handling **MongoDB Atlas** and **AWS S3**
* Modular **Python architecture**
* CI/CD automation using **GitHub Actions**
* Production-ready deployment on **EC2 + Docker**

---

## 🔗 Useful Links

* MongoDB Atlas: [https://www.mongodb.com/cloud/atlas](https://www.mongodb.com/cloud/atlas)
* AWS: [https://aws.amazon.com](https://aws.amazon.com)
* Docker: [https://www.docker.com](https://www.docker.com)
* GitHub Actions: [https://docs.github.com/en/actions](https://docs.github.com/en/actions)

---

## 💡 Author

**Dev Saxena** – MLOps & Cloud Practitioner
[LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/devsaxena817)

---

> 🚀 *This repository is a showcase of hands-on experience in designing, deploying, and automating end-to-end ML pipelines for real-world applications.*

```

---

```
