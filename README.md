# 🇧🇩 Bangladesh Multi-Tool AI Agent

> An intelligent Bangladesh-focused Multi-Tool AI Agent built with **LangChain, Google Gemini, Hugging Face Datasets, SQLite, and Tavily Search**.

<p align="center">

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00?logo=googlecolab)
![LangChain](https://img.shields.io/badge/LangChain-AI%20Agent-green)
![Gemini](https://img.shields.io/badge/Google-Gemini-orange)
![SQLite](https://img.shields.io/badge/Database-SQLite-blue?logo=sqlite)
![HuggingFace](https://img.shields.io/badge/🤗-Hugging%20Face-yellow)
![License](https://img.shields.io/badge/License-MIT-green)

</p>

---

## 📌 Project Overview

**Bangladesh Multi-Tool AI Agent** is an intelligent AI agent designed to answer Bangladesh-related questions by automatically selecting the most appropriate tool.

The system combines:

* 🤖 Google Gemini 2.5 Flash
* 🔗 LangChain Agent Framework
* 🗄️ SQLite Databases
* 🤗 Hugging Face Datasets
* 🔍 Tavily Web Search
* 🐼 Pandas
* 📓 Google Colab

The agent can answer questions related to:

* 🎓 Educational Institutions
* 🏥 Hospitals and Health Facilities
* 🍽️ Restaurants
* 🌐 General Bangladesh Information
* 🔎 Current Information through Web Search

---

# 🚀 Run on Google Colab

This project is designed to run directly on **Google Colab**.

### Step 1: Open Google Colab

Open:

https://colab.research.google.com/

### Step 2: Upload the Notebook

Upload:

```text
bangladesh_multi_tool_ai_agent.ipynb
```

### Step 3: Add API Keys

The project requires:

```text
GOOGLE_API_KEY
TAVILY_API_KEY
```

In Google Colab:

1. Click the **🔑 Secrets** icon.
2. Add:

```text
GOOGLE_API_KEY
```

3. Add:

```text
TAVILY_API_KEY
```

4. Enable notebook access for both secrets.

### Step 4: Run All Cells

From the Colab menu:

```text
Runtime → Run all
```

The notebook will automatically:

```text
Install Dependencies
        ↓
Load API Keys
        ↓
Download Bangladesh Datasets
        ↓
Convert Data to Pandas DataFrames
        ↓
Create SQLite Databases
        ↓
Create LangChain Tools
        ↓
Initialize Gemini
        ↓
Create AI Agent
        ↓
Run Test Queries
        ↓
Start Interactive AI Agent
```

---

# 🏗️ System Architecture

```text
                         ┌─────────────────────┐
                         │     User Query      │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   LangChain Agent   │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Gemini 2.5 Flash LLM│
                         └──────────┬──────────┘
                                    │
                         Intelligent Tool Routing
                                    │
          ┌─────────────────────────┼─────────────────────────┐
          │                         │                         │
          ▼                         ▼                         ▼

┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐
│ Institutions DB │      │  Hospitals DB   │      │ Restaurants DB  │
│   SQLite Tool   │      │   SQLite Tool   │      │   SQLite Tool   │
└─────────────────┘      └─────────────────┘      └─────────────────┘

                                    │
                                    │
                                    ▼

                         ┌─────────────────────┐
                         │   WebSearchTool     │
                         │       Tavily        │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   Final Response    │
                         └─────────────────────┘
```

---

# 🧰 Available Tools

The AI Agent uses four major tools.

## 🎓 1. InstitutionsDBTool

Used for questions related to:

* Universities
* Colleges
* Schools
* Educational Institutions
* EIIN Numbers
* Institution Counts
* District-based Institution Queries

Example:

```text
How many institutions are in Rajshahi?
```

Example routing:

```text
User Question
      ↓
Gemini Agent
      ↓
InstitutionsDBTool
      ↓
SQLite Database
      ↓
SQL Query
      ↓
Final Answer
```

---

## 🏥 2. HospitalsDBTool

Used for questions related to:

* Hospitals
* Health Facilities
* Clinics
* District-based Health Information
* Hospital Counts

Example:

```text
How many hospitals are in Dhaka?
```

Example:

```text
List 10 hospitals in Chattogram.
```

---

## 🍽️ 3. RestaurantsDBTool

Used for:

* Restaurant Search
* Restaurant Ratings
* Restaurant Reviews
* Restaurant Addresses
* Location-based Restaurant Queries

Example:

```text
Find 10 restaurants in Chattogram.
```

Example:

```text
Which restaurants have ratings above 4.5?
```

---

## 🌐 4. WebSearchTool

Powered by **Tavily Search**.

Used when the requested information is:

* Not available in local databases
* Current or time-sensitive
* General information
* Government information
* Policy-related information
* Bangladesh-related external knowledge

Example:

```text
What is the role of DGHS in Bangladesh?
```

Routing:

```text
User Question
      ↓
Gemini Agent
      ↓
WebSearchTool
      ↓
Tavily Search
      ↓
External Information
      ↓
Final Answer
```

---

# 📊 Datasets

The project uses Bangladesh-focused datasets from Hugging Face.

## 🎓 Educational Institutions

```text
Mahadih534/Institutional-Information-of-Bangladesh
```

Used for:

* Institution names
* Educational information
* EIIN-related information
* Location-based queries

---

## 🏥 Hospitals

```text
Mahadih534/all-bangladeshi-hospitals
```

Used for:

* Hospital information
* Health facilities
* Location-based hospital queries

---

## 🍽️ Restaurants

```text
Mahadih534/Bangladeshi-Restaurant-Data
```

Used for:

* Restaurant names
* Ratings
* Reviews
* Addresses

---

# 🔄 Data Pipeline

The project follows this pipeline:

```text
Hugging Face Dataset
        │
        ▼
Load Dataset
        │
        ▼
Pandas DataFrame
        │
        ▼
Data Cleaning / Processing
        │
        ▼
CSV Storage
        │
        ▼
SQLite Database
        │
        ▼
LangChain Tool
        │
        ▼
AI Agent
```

---

# 🔐 Database Security

The database tools are designed to use **read-only SQL operations**.

### Allowed

```sql
SELECT *
FROM hospitals
LIMIT 10;
```

```sql
WITH ranked_data AS (
    SELECT *
    FROM restaurants
)
SELECT *
FROM ranked_data;
```

### Blocked

```sql
INSERT
UPDATE
DELETE
DROP
ALTER
```

The purpose is to prevent destructive database operations.

---

# 🤖 AI Agent Workflow

```text
                    USER QUESTION
                          │
                          ▼
                  LANGCHAIN AGENT
                          │
                          ▼
                    GEMINI LLM
                          │
                          ▼
              ┌──────────────────────┐
              │  Which Tool to Use?  │
              └───────────┬──────────┘
                          │
       ┌──────────────────┼──────────────────┐
       │                  │                  │
       ▼                  ▼                  ▼

Institutions DB       Hospitals DB      Restaurants DB

                          │
                          ▼

                      Web Search
                          │
                          ▼

                     FINAL ANSWER
```

---

# 💻 Google Colab Setup

## Step 1: Install Required Libraries

Run the installation cell:

```python
!pip install -q \
langchain \
langchain-classic \
langchain-core \
langchain-community \
langchain-google-genai \
langchain-openai \
tavily-python \
datasets \
pandas \
python-dotenv \
pytest
```

---

## Step 2: Import Required Libraries

Example:

```python
import os
import sqlite3
import pandas as pd

from datasets import load_dataset
from google.colab import userdata
```

For LangChain and Gemini:

```python
from langchain_google_genai import ChatGoogleGenerativeAI
```

---

## Step 3: Load API Keys from Colab Secrets

```python
GOOGLE_API_KEY = userdata.get("GOOGLE_API_KEY")
TAVILY_API_KEY = userdata.get("TAVILY_API_KEY")
```

Check:

```python
if not GOOGLE_API_KEY:
    raise ValueError("GOOGLE_API_KEY is missing.")

if not TAVILY_API_KEY:
    raise ValueError("TAVILY_API_KEY is missing.")
```

---

## Step 4: Load Gemini Model

```python
llm = ChatGoogleGenerativeAI(
    model="gemini-2.5-flash",
    temperature=0,
    google_api_key=GOOGLE_API_KEY
)
```

---

# 🗄️ SQLite Database

The datasets are converted into SQLite databases.

Example:

```python
import sqlite3

conn = sqlite3.connect("institutions.db")

df.to_sql(
    "institutions",
    conn,
    if_exists="replace",
    index=False
)

conn.close()
```

The same architecture can be used for:

```text
institutions.db
hospitals.db
restaurants.db
```

---

# 🧪 Example Questions

## 🎓 Educational Institutions

```text
How many institutions are in Rajshahi?
```

```text
List 10 institutions in Dhaka.
```

```text
Find educational institutions in Chattogram.
```

---

## 🏥 Hospitals

```text
How many hospitals are in Dhaka?
```

```text
List 10 health facilities in Chattogram.
```

```text
Find hospitals in Rajshahi.
```

---

## 🍽️ Restaurants

```text
Find 10 restaurants in Chattogram.
```

```text
Which restaurants have ratings above 4.5?
```

```text
Show restaurants in Dhaka.
```

---

## 🌐 General Information

```text
What is the role of DGHS in Bangladesh?
```

```text
What is the healthcare policy in Bangladesh?
```

```text
Tell me about Bangladesh's education system.
```

---

# 💬 Interactive Mode

The notebook includes an interactive AI agent.

Example:

```text
======================================================================
🇧🇩 BANGLADESH MULTI-TOOL AI AGENT
======================================================================

Type 'exit' to stop.

You:
```

Example interaction:

```text
You: Find 10 restaurants in Chattogram

🤖 Agent:

Here are 10 restaurants in Chattogram...
```

To stop:

```text
exit
```

or:

```text
quit
```

---

# ⚠️ API Quota Issue

During testing, the Google Gemini API may return:

```text
429 RESOURCE_EXHAUSTED
```

Example:

```text
You exceeded your current quota.
```

Possible solutions:

1. Wait for the quota to reset.
2. Reduce repeated API calls.
3. Check Google AI API quota and billing.
4. Implement retry logic.
5. Use a supported model/API configuration according to your available quota.

---

# 🔄 Recommended Retry Logic

For production improvement:

```python
import time

def retry_agent(question, retries=3):

    for attempt in range(retries):

        try:
            return ask_agent(question)

        except Exception as error:

            print(f"Attempt {attempt + 1} failed.")

            time.sleep(10)

    return "Unable to process the request."
```

---

# 📁 Recommended GitHub Repository Structure

Since this is a **Google Colab-based project**, a simple repository structure is recommended:

```text
bangladesh-multi-tool-ai-agent/
│
├── bangladesh_multi_tool_ai_agent.ipynb
│
├── README.md
│
├── requirements.txt
│
├── .gitignore
│
└── LICENSE
```

Optional future structure:

```text
bangladesh-multi-tool-ai-agent/
│
├── notebooks/
│   └── bangladesh_multi_tool_ai_agent.ipynb
│
├── src/
│   ├── database_tools.py
│   ├── web_search.py
│   └── agent.py
│
├── tests/
│
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE
```

---

# 📦 requirements.txt

Create a file named:

```text
requirements.txt
```

Add:

```text
langchain>=1.0.0
langchain-classic>=1.0.0
langchain-core>=1.0.0
langchain-community>=0.4.0
langchain-google-genai>=4.0.0
langchain-openai>=1.0.0
tavily-python>=0.7.0
datasets>=3.0.0
pandas>=2.2.0
python-dotenv>=1.0.1
pytest>=8.0.0
```

---

# 🙈 .gitignore

Create:

```text
.gitignore
```

Add:

```gitignore
__pycache__/
*.pyc

.env

.ipynb_checkpoints/

*.db

data/raw/*.csv

.DS_Store
```

**Important:** Never upload API keys to GitHub.

---

# 📤 Upload to GitHub

## Step 1: Create Repository

Recommended repository name:

```text
https://github.com/Ferdaus71/bangladesh-multi-tool-ai-agent
```

Recommended description:

```text
A Bangladesh-focused Multi-Tool AI Agent built with LangChain, Gemini, SQLite, Hugging Face Datasets, and Tavily Search.
```

---

## Step 2: Upload Files

Upload:

```text
bangladesh_multi_tool_ai_agent.ipynb
README.md
requirements.txt
.gitignore
```

---

## Step 3: Commit Message

Use:

```text
feat: initial release of Bangladesh multi-tool AI agent
```

For future updates:

```text
feat: add new database tool
```

```text
fix: improve Gemini error handling
```

```text
docs: update project documentation
```

```text
test: add database security tests
```

---

# 🧪 Testing

Recommended testing areas:

```text
✓ Dataset loading
✓ SQLite database creation
✓ Database connection
✓ SQL query validation
✓ Read-only SQL security
✓ Tool routing
✓ Empty query handling
✓ Missing field handling
✓ Web search fallback
✓ API error handling
```

---

# 🛡️ Important Design Principles

## 1. Tool-Based Architecture

The agent chooses tools based on the user question.

---

## 2. No Hallucination

The AI should not invent database values.

If a field is not available:

```text
Hospital Bed Capacity
ICU Capacity
Doctor Count
```

The agent should clearly state that the information is unavailable.

---

## 3. Schema Awareness

The AI agent should only query fields that actually exist in the database.

---

## 4. Read-Only Database Access

Database tools should not modify or delete data.

---

## 5. Web Search Fallback

If information is not available in the local datasets, the agent can use Tavily Search.

---

# 📈 Future Improvements

## Phase 1 — Code Improvement

* [ ] Improve error handling
* [ ] Add retry logic
* [ ] Add logging
* [ ] Add better tool descriptions
* [ ] Improve prompt engineering
* [ ] Add more tests

## Phase 2 — New Bangladesh Tools

* [ ] Transport Database
* [ ] Tourism Database
* [ ] Government Services Database
* [ ] Job Information Tool
* [ ] Weather Tool
* [ ] University Information Tool

## Phase 3 — Web Application

* [ ] Streamlit UI
* [ ] FastAPI Backend
* [ ] REST API
* [ ] Chat History
* [ ] Source Citations

## Phase 4 — Production Deployment

* [ ] Docker
* [ ] CI/CD
* [ ] PostgreSQL
* [ ] Cloud Deployment
* [ ] Monitoring
* [ ] Authentication
* [ ] Evaluation System

---

# 🤝 Contributing

Contributions are welcome.

### 1. Fork the Repository

### 2. Create a Branch

```bash
git checkout -b feature/new-feature
```

### 3. Make Changes

### 4. Commit Changes

```bash
git add .
```

```bash
git commit -m "feat: add new feature"
```

### 5. Push

```bash
git push origin feature/new-feature
```

### 6. Create a Pull Request

---

# 📄 License

This project is intended for:

* Educational purposes
* Research
* AI experimentation
* Bangladesh-focused data applications

You can add an MIT License for open-source distribution.

---

# 🙏 Acknowledgements

Special thanks to:

* **LangChain** — AI Agent Framework
* **Google Gemini** — Large Language Model
* **Tavily** — AI Web Search
* **Hugging Face** — Dataset Platform
* **Pandas** — Data Processing
* **SQLite** — Lightweight Database
* **Google Colab** — Cloud Notebook Environment

---

# 👨‍💻 Author

## Md. Ferdaus Hossen

**AI/ML Engineer | AI Researcher | Data & AI Enthusiast**

🔗 **GitHub:**
https://github.com/Ferdaus71

🔗 **LinkedIn:**
https://linkedin.com/in/ferdaus71

🌐 **Portfolio:**
https://ferdaus71.github.io/Portfolio/

---

# ⭐ Support

If you find this project useful:

⭐ Star the repository

🍴 Fork the project

🐛 Report issues

💡 Suggest improvements

🤝 Contribute to the project

---

<p align="center">

Made with ❤️ in Bangladesh 🇧🇩

<br>

**Md. Ferdaus Hossen**

</p>
