# 📘 **README — Iris MLflow Model (with Docker)**

This project trains a simple **Random Forest classifier** on the Iris dataset and uses **MLflow** to track metrics, parameters, and models.
You can run it **locally** or inside **Docker**.

---

## 🚀 Features

* Train an Iris classification model
* Track metrics, params, and artifacts using **MLflow**
* Containerized execution using **Docker**
* View MLflow UI in your browser

---

# 📦 **1. Setup (Without Docker)**

### **Install dependencies**

`pip install -r requirements.txt`

### **Run the training script**

`python model.py`

This will:

* Train a RandomForest model
* Log metrics and parameters to `mlruns/`
* Save the model as an MLflow artifact

---

# 📊 **2. View MLflow UI**

Start MLflow UI:

`mlflow ui`

Open in your browser:

http://127.0.0.1:5000

You can explore:

* **Metrics** (accuracy)
* **Parameters** (n_estimators, etc.)
* **Artifacts** (saved model)
* **Run history**

---

# 🐳 **3. Running with Docker**

### **Build the Docker image**

`docker build -t iris-mlflow .`


### **Run the model inside Docker**

`docker run --rm iris-mlflow`

### **Persist MLflow runs outside the container**

#### Windows PowerShell:

`docker run --rm -v "${PWD}/mlruns:/app/mlruns" iris-mlflow`

#### Linux / Mac:

`docker run --rm -v $(pwd)/mlruns:/app/mlruns iris-mlflow`

Your MLflow tracking files will now appear locally in:

./mlruns/

---

# 🌐 **4. Run MLflow UI in Docker**

If you modified the Dockerfile to expose the UI, run:

`docker run -p 5000:5000 -v $(pwd)/mlruns:/app/mlruns iris-mlflow`

Open:

http://127.0.0.1:5000

---

# 📁 **5. Project Structure**

```
.
├── model.py
├── requirements.txt
├── Dockerfile
├── README.md
└── mlruns/          # MLflow run history (ignored by Git)
```

---

# 🧹 **6. .gitignore (Recommended)**

```
mlruns/
__pycache__/
*.pyc
.venv/
env/
.vscode/
*.log
```

---

# 🎉 **Done!**

You should now have a fully working:

* MLflow experiment
* Dockerized training script
* Local persistence for metrics
* MLflow UI dashboard


