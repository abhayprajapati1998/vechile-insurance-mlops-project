# vechile-insurance-mlops-project
This `README.md` file describe all the process/method required for a ML end to end.
# 🚗 Vehicle Data ML Pipeline - End-to-End MLOps Project

Welcome to an enterprise-grade **MLOps Pipeline for Vehicle Data**!  
This repository demonstrates how to build, deploy, and scale a machine learning solution using modern MLOps practices and cloud-native tools.

> ⚙️ From **project scaffolding** to **CI/CD deployment on AWS**, this project is designed to give you a complete walkthrough of how production-ready ML systems are built.

---

## 📌 Project Highlights

- 🔧 **Project Scaffold Automation** via `template.py`
- 📦 **Modular Code Packaging** using `setup.py` & `pyproject.toml`
- 📊 **MongoDB Integration** for seamless data ingestion
- 🧠 **ML Workflow**: EDA → Data Ingestion → Validation → Transformation → Training → Evaluation → Prediction
- ☁️ **AWS Integration**: Model registry in S3, Deployment via EC2 & ECR
- 🔁 **CI/CD Pipeline** using GitHub Actions & Self-Hosted Runner
- 🐳 **Dockerized Deployment** for scalable, cloud-native inference
- 📈 **Live Prediction Web App** on EC2

---

## 🚀 Getting Started

### 🧱 1. Project Setup

```bash
# Create template structure
python template.py

# Setup Python virtual environment
conda create -n vehicle python=3.10 -y
conda activate vehicle

# Install dependencies
pip install -r requirements.txt

# Confirm installation
pip list
```

---

### 🌱 2. Local Package Management

Set up your project for local imports using:
- `setup.py`
- `pyproject.toml`

📘 *More details in `crashcourse.txt`*

---

### 🌐 3. MongoDB Atlas Configuration

1. Create MongoDB Atlas account and cluster (M0 tier)
2. Setup DB user and IP access (`0.0.0.0/0`)
3. Copy the connection string for your project
4. Push local dataset to MongoDB using `mongoDB_demo.ipynb`

> 💡 Validate your MongoDB data using the Atlas dashboard (key-value format)

---

### 🛠 4. Logging, Exceptions & Notebooks

- ✅ Custom logger integrated and tested
- ⚠️ Centralized exception handling
- 📔 EDA & Feature Engineering notebooks ready

---

### 🧩 5. Modular ML Pipeline Components

#### 🔹 Data Ingestion
- Configuration via `constants` and `entity` modules
- Data fetched from MongoDB and converted to DataFrame

#### 🔹 Data Validation
- Schema-defined validation using `config/schema.yaml`

#### 🔹 Data Transformation
- Transformers and estimators for scaling and encoding

#### 🔹 Model Trainer
- Train and persist ML model using structured pipeline

---

### ☁️ 6. AWS Setup for Model Evaluation & Pushing

1. Create IAM user with `AdministratorAccess`
2. Set `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY` via environment variables
3. Create S3 bucket: `my-model-mlopsproj`
4. Implement S3 interaction logic (`aws_connection.py`, `s3_estimator.py`)

> 📦 Models are versioned and pushed to S3 after evaluation

---

### 🧪 7. Model Evaluation & Pusher

- Compare current vs previous model using defined threshold
- Push best model to model registry (S3) for inference

---

### 🧾 8. Prediction Pipeline

- REST API served via `Flask` in `app.py`
- Frontend templating with HTML in `template/`
- Static assets in `static/`

---

## 🔁 CI/CD Workflow

### 🔧 Dockerization

- `Dockerfile` & `.dockerignore` setup
- App containerized for seamless deployment

### 🛠 GitHub Actions

- CI/CD pipeline defined in `.github/workflows/aws.yaml`
- Secrets configured in GitHub repo settings

### 🚀 AWS ECR & EC2

- Docker images pushed to **AWS ECR**
- Web app hosted on **AWS EC2 (Ubuntu Server 24.04)**

### 🧑‍💻 Self-Hosted GitHub Runner

- EC2 configured as GitHub Runner for end-to-end CI/CD
- Port 5000 opened to allow web access

---

## 🔗 Final Deployment

- ✅ Push to GitHub → CI/CD triggered → Docker image built → Pushed to ECR
- ✅ EC2 pulls and runs latest image
- 🌐 Access the live app via:
  ```
  http://<your-ec2-public-ip>:5000
  ```

- 🏋️ Trigger training manually from:
  ```
  http://<your-ec2-public-ip>:5000/training
  ```

---

## 📚 Folder Structure

```
📁 src/
│   ├── configuration/
│   ├── components/
│   ├── entity/
│   ├── pipeline/
│   ├── aws_storage/
│   └── utils/
📁 notebook/
📁 templates/
📁 static/
📄 app.py
📄 setup.py
📄 requirements.txt
📄 pyproject.toml
```

---

## ✅ Key Technologies Used

| Category           | Tools & Services                                      |
|--------------------|-------------------------------------------------------|
| Programming        | Python 3.10                                           |
| Data Storage       | MongoDB Atlas                                         |
| ML Workflow        | pandas, scikit-learn, PyYAML                          |
| Cloud Services     | AWS S3, EC2, ECR, IAM                                 |
| Deployment         | Docker, Flask, GitHub Actions                         |
| CI/CD              | GitHub Actions, Self-Hosted Runner on EC2             |
| Orchestration      | Conda, Environment Variables                          |

---

## 💬 Want to Connect?

📧 [Email](mailto:abhay.pra.s@gmail.com)  
🔗 [LinkedIn](https://www.linkedin.com/in/abhay-prajapati-2a36b8157/)  
📁 [Portfolio](https://github.com/abhayprajapati1998)

---

> 👨‍💻 Built with ❤️ by Abhay Prajapati — Designed to make ML projects **production-ready** from Day 1!