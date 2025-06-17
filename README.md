# 🧠 Log Classification System

A smart log classification system that determines the client associated with a log using Regex, BERT, or LLMs (via Groq API). It features a FastAPI backend to serve predictions programmatically.

---

## 💻 Tech Stack

### ⚙️ Core Technologies
- **Python** – Primary language
- **FastAPI** – Backend API framework
- **Scikit-learn** – For training and saving classification models
- **Hugging Face Transformers** – For BERT-based log classification
- **Regex (re module)** – For rule-based log parsing
- **Groq LLM API** – For inference using large language models
- **Uvicorn** – ASGI server for running FastAPI apps
- **joblib** – Model persistence and loading
- **dotenv** – Managing API keys and environment variables

### 📦 Dev & Tooling
- **VS Code** – Development environment
- **Jupyter Notebook** – For experiments and training
- **Git** – Version control
- **`.env` + `.gitignore`** – Secure secret handling

---

## 🧠 Classification Approaches

The system intelligently selects the best classification method for each input log, depending on its complexity and available data.

### 1. Regular Expression (Regex):
- Handles the most simplified and predictable log patterns.
- Ideal for logs that match clear, predefined rules.

### 2. Sentence Transformer + Logistic Regression:
-  Manages moderately complex patterns where sufficient labeled training data exists.
-  Uses Sentence Transformers to generate embeddings and applies Logistic Regression as the classification layer.

### 3. LLM (Large Language Models):
-  Suitable for highly complex patterns or when labeled training data is limited or unavailable.
-  Acts as a fallback or complementary classifier, utilizing external inference through Groq API.

---

## 📂 Project Structure
```
Project_Log_Classification_System/
│
├── models/ # Contains the trained joblib model
│ └── log_classifier.joblib
│
├── resources/ # Supporting data files
│ ├── output.csv
│ └── test.csv
│
├── training/ # Training-related files
│ └── dataset/
│ └── synthetic_logs.csv
│
├── classify.py # Handles input preprocessing & classifier execution
├── processor_bert.py # BERT-based classification logic
├── processor_llm.py # LLM (Groq API) based classification logic
├── processor_regex.py # Regex rule-based classification logic
├── server.py # FastAPI app exposing the classification API
├── log_classification.ipynb # Notebook for experimentation and training
├── requirements.txt # Python dependencies
├── .env # Environment variables (not tracked in Git)
└── .gitignore # Git ignore rules
``` 


---

## 🚀 Features

- 🔍 Rule-based classification with regex
- 🤖 Fine-tuned or pretrained BERT for semantic understanding
- 🧠 LLM-based classification using Groq API for intelligent fallback
- 🌐 API endpoints using FastAPI
- 📚 Jupyter notebook for data exploration and training
- 🔐 Secure handling of API keys with `.env`

---

## ⚙️ Setup Instructions

1. **Clone the repository**

```
git clone https://github.com/yourusername/Project2_Log_Classification_System.git
cd Project2_Log_Classification_System
```

2. **Install dependencies**

```
pip install -r requirements.txt
```
3. **Create a .env file**

```
GROQ_API_KEY=your_groq_api_key_here
```
✅ Make sure .env is not tracked by Git — it's in .gitignore.

4. **Run the FastAPI server**
```
uvicorn server:app --reload
```
- Navigate to: http://127.0.0.1:8000/docs to access Swagger UI for testing the endpoints.
---
## 🧪 API Testing
Use the /classify endpoint via:

-  Swagger UI

-  cURL/Postman

-  Python requests

The backend selects the appropriate classification method based on the log content or client requirement.

--- 

## 📌 Notes

Regenerate your Groq API key if you accidentally pushed it to GitHub.

Add a .env.example for contributors.

---

## 📜 License
-MIT License – feel free to use and modify.

---

## ✍️ Author
Vaibhav Devaraj
Machine Learning Engineer , Passionate about AI, automation, and modular system design.
