# 🇧🇩 Bangladesh Multi-Tool AI Agent

> A LangChain-based multi-tool AI agent that intelligently answers Bangladesh-specific questions using structured datasets, SQLite databases, Google Gemini, and Tavily Web Search.

<p align="center">

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-Agent-1C3C3C?logo=langchain&logoColor=white)
![Gemini](https://img.shields.io/badge/Google-Gemini-4285F4?logo=google&logoColor=white)
![SQLite](https://img.shields.io/badge/Database-SQLite-003B57?logo=sqlite&logoColor=white)
![Tavily](https://img.shields.io/badge/Web_Search-Tavily-7C3AED)
![Pandas](https://img.shields.io/badge/Pandas-Data_Processing-150458?logo=pandas&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Datasets-HuggingFace-FFD21E?logo=huggingface&logoColor=black)
![Google Colab](https://img.shields.io/badge/Run-Google_Colab-F9AB00?logo=googlecolab&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

</p>

---

## 📌 Project Overview

**Bangladesh Multi-Tool AI Agent** is an intelligent tool-using AI system designed to answer questions related to Bangladesh by selecting the most appropriate information source.

The system combines:

- Structured Bangladesh datasets
- SQLite databases
- LangChain tools
- Google Gemini LLM
- Tavily Web Search
- Read-only SQL execution
- Intelligent tool routing
- Schema-aware database querying

Instead of depending entirely on the language model's internal knowledge, the agent can retrieve factual information directly from local Bangladesh datasets.

For questions that require general, current, policy-related, or external information, the agent can use web search.

---

# 🎯 Project Objectives

The primary objectives of this project are:

- Build a practical AI agent using LangChain.
- Integrate multiple specialized tools.
- Convert Bangladesh datasets into SQLite databases.
- Create database query tools for different domains.
- Integrate web search for general knowledge.
- Automatically route user queries to the appropriate tool.
- Execute only read-only SQL queries.
- Reduce hallucination by grounding answers in structured data.
- Detect unavailable database fields instead of inventing information.
- Provide a reusable and professional AI-agent architecture.

---

# 🏗️ System Architecture

```text
                         ┌─────────────────────────┐
                         │       USER QUERY        │
                         └────────────┬────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────┐
                         │    LANGCHAIN AGENT      │
                         │      + GEMINI LLM       │
                         └────────────┬────────────┘
                                      │
                    ┌─────────────────┼─────────────────┐
                    │                 │                 │
                    ▼                 ▼                 ▼
          ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
          │ Institutions    │ │    Hospitals    │ │   Restaurants   │
          │    DB Tool      │ │     DB Tool     │ │     DB Tool     │
          └────────┬────────┘ └────────┬────────┘ └────────┬────────┘
                   │                   │                   │
                   ▼                   ▼                   ▼
          ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
          │ institutions.db │ │  hospitals.db   │ │ restaurants.db  │
          └─────────────────┘ └─────────────────┘ └─────────────────┘

                                      OR

                         ┌─────────────────────────┐
                         │     WebSearchTool       │
                         │         Tavily          │
                         └────────────┬────────────┘
                                      │
                                      ▼
                              External Web Data
