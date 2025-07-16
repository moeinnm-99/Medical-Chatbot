
---

# 🧠 Medical Chatbot

<img src="https://github.com/moeinnm-99/Medical-Chatbot/blob/main/Medical-Chatbot.png"></img>

A powerful AI-driven medical chatbot built using **Python**, **LangChain**, **OpenAI GPT**, **Pinecone**, and **Flask**. It allows users to ask health-related questions and get intelligent responses powered by large language models.

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Flask](https://img.shields.io/badge/Flask-2.x-black?logo=flask)
![LangChain](https://img.shields.io/badge/LangChain-%2300BFFF)
![Pinecone](https://img.shields.io/badge/Pinecone-VectorDB-green)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-black?logo=openai)

---

## 🚀 Features

- Conversational interface powered by GPT
- Intelligent vector search using Pinecone
- Modular LLM logic using LangChain
- Lightweight Flask web server
- Dockerized & deployable to AWS via GitHub Actions

---

## 📦 Tech Stack

| Layer             | Technology          |
|------------------|---------------------|
| Backend          | Python, Flask       |
| LLM Framework    | LangChain           |
| Vector Database  | Pinecone            |
| LLM Provider     | OpenAI (GPT-4)      |
| Deployment       | AWS EC2, Docker     |
| CI/CD            | GitHub Actions      |

---

## 🛠️ Setup Instructions

### ✅ Clone the Repository

```bash
git clone https://github.com/moeinnm-99/Medical-Chatbot.git
cd Medical-Chatbot
````

---

### ✅ Create and Activate Conda Environment

#### 🪟 For **Windows** Users:

```bash
conda create -n medibot python=3.10 -y
conda activate medibot
```

#### 🐧 For **Linux/macOS** Users:

```bash
conda create -n medibot python=3.10 -y
source activate medibot    # or just use: conda activate medibot
```

> ⚠️ If `conda activate` doesn’t work, run:

```bash
conda init
```

Then restart your terminal.

---

### ✅ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔐 Setup Environment Variables

Create a `.env` file in the root directory and add the following credentials:

```ini
OPENAI_API_KEY=your_openai_api_key
PINECONE_API_KEY=your_pinecone_api_key
```

---

## 📤 Index Medical Data

To generate and store embeddings in Pinecone:

```bash
python store_index.py
```

---

## ▶️ Run the Application

Start the Flask server:

```bash
python app.py
```

Then open your browser and visit:

```
http://localhost:5000
```

---

## ☁️ AWS CI/CD Deployment Guide

### 1. Login to AWS Console

### 2. Create IAM User with Required Permissions

Assign the following AWS policies to the user:

* `AmazonEC2FullAccess`
* `AmazonEC2ContainerRegistryFullAccess`

### 3. Create ECR Repository

Example ECR URI:

```
315865595366.dkr.ecr.us-east-1.amazonaws.com/medibot
```

### 4. Launch an EC2 Instance

* Use Ubuntu
* Open port `5000` in your security group

### 5. Install Docker on EC2

```bash
sudo apt-get update -y
sudo apt-get upgrade -y
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

---

### 6. Set up EC2 as GitHub Self-Hosted Runner

In your GitHub repo:

```
Settings → Actions → Runners → New self-hosted runner
```

Follow the instructions for **Linux**, and run all the setup commands provided.

---

### 7. Configure GitHub Secrets

Add the following to your GitHub repository secrets:

| Secret Name             | Description           |
| ----------------------- | --------------------- |
| `AWS_ACCESS_KEY_ID`     | Your IAM access key   |
| `AWS_SECRET_ACCESS_KEY` | Your IAM secret key   |
| `AWS_DEFAULT_REGION`    | e.g., `us-east-1`     |
| `ECR_REPO`              | ECR repo URI          |
| `OPENAI_API_KEY`        | Your OpenAI API Key   |
| `PINECONE_API_KEY`      | Your Pinecone API Key |

---

## 🐳 Docker (Optional Local Run)

Build and run the Docker container locally:

```bash
docker build -t medibot .
docker run -p 5000:5000 --env-file .env medibot
```

---

## 🧪 Future Improvements

* ✅ Add user authentication
* ⏳ Integrate voice-to-text input
* ⏳ Enable chat history logging
* ⏳ Add frontend UI using Streamlit or React

---

## 📫 Contact

**Moein Namdari**
🔗 [GitHub](https://github.com/moeinnm-99)
📧 [moeinnm.99@gmail.com](mailto:moeinnm.99@gmail.com)

---

## 🌟 Support

If you found this project helpful, feel free to give it a ⭐ on [GitHub](https://github.com/moeinnm-99/Medical-Chatbot)!

---

