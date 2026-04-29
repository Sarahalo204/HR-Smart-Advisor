# 📖 HR Smart Advisor: Multi-Agent RAG System

A sophisticated AI-driven advisory system specialized in Saudi Arabian Human Resources laws and regulations. The system utilizes a **Multi-Agent Architecture** and **Retrieval-Augmented Generation (RAG)** to provide accurate, cited, and audited answers from internal documents (PDFs) and live web sources.

---

## 🚀 Technical Stack

This project is built using a modern AI stack designed for production-grade observability and performance:

* **Core Engine:** Python 3.10+
* **LLM Orchestration:** Gemini 2.0 Flash via OpenRouter/LiteLLM
* **Agent Framework:** Custom **ReAct** (Reasoning + Acting) implementation with full observability
* **RAG System:**
* **Embeddings:** `multilingual-e5-base` for high-accuracy Arabic/English semantic search.
* **Processing:** `RecursiveChunker` for intelligent document splitting.


* **Observability:**
* **Tracing:** Step-by-step execution logging.
* **Cost Tracking:** Real-time USD cost calculation per query.
* **Loop Detection:** Advanced prevention of repetitive agent actions.


* **Interface:** Streamlit for an interactive, user-friendly dashboard.

---

## 🏗️ Project Structure

The repository is organized into modular components for easy maintenance and scaling:

```text
LAB1_SDAIA/
├── SDAIA-Building-Gen-AI-Apps/
│   └── project_starter/
│       ├── src/
│       │   ├── agent/             # Agent logic (ObservableAgent & Specialist Factories)
│       │   ├── observability/     # Cost tracking, Tracing, and Loop Detection
│       │   ├── tools/             # Registered tools (Web Search, RAG Search, Web Scraper)
│       │   ├── rag/               # RAG Engine and document ingestion logic
│       │   ├── documents/         # Local Knowledge Base (Place your PDFs here)
│       │   ├── app.py             # Streamlit Web Application
│       │   └── main.py            # CLI entry point
│       ├── requirements.txt       # Project dependencies
│       └── .env                   # Environment variables (API Keys)
└── .venv/                         # Virtual Environment

```

---

## 🧠 The Agent Pipeline

The system employs a linear "Chain of Thought" involving three specialized agents:

1. **Researcher Agent:**
* **Primary Task:** Fact retrieval.
* **Logic:** Searches the **Internal Knowledge Base** first. If data is missing or incomplete, it is mandated to perform a **Web Search** as a fallback.


2. **Analyst Agent:**
* **Primary Task:** Logical synthesis.
* **Logic:** Interprets raw search results, cross-references articles, and identifies legal patterns or gaps.


3. **Writer Agent:**
* **Primary Task:** Final report generation.
* **Logic:** Formats the analysis into a professional, empathetic Arabic response with clear executive summaries and references.



---

## 🛠️ Getting Started

### 1. Environment Setup

Activate your virtual environment and install the required dependencies:

```bash
# Activation (Windows)
.\.venv\Scripts\activate

# Install requirements
pip install -r requirements.txt

```

### 2. Configuration

Create a `.env` file in the `project_starter` directory:

```env
OPENROUTER_API_KEY=your_api_key_here # or any api Key
MODEL_NAME=openrouter/google/gemini-2.0-flash-001 or any model 

```

### 3. Running the Application

**Via CLI:**

```bash
python -m src.main "What are the employee rights for sick leave?"

```

**Via Streamlit (Web UI):**

```bash
streamlit run src/app.py

```

---

## 🔍 Key Features

* **Zero-Hallucination Guard:** Agents are strictly instructed to use provided tools and cite sources (File names or URLs) for every factual claim.
* **Production Observability:** Every query generates a unique `trace_id` allowing developers to debug the exact reasoning path taken by the AI.
* **Bilingual Support:** Optimized for Saudi Labor Law in Arabic, while maintaining the ability to process English queries.
* **Automatic Ingestion:** Simply drop PDF files into `src/documents/`, and the system will automatically index them into the RAG engine upon startup.

---

# Course Materials Distribution

Welcome to the distribution of the course materials. This folder contains all the necessary resources for your labs and homework, excluding the solutions.

## Getting Started

### 1. Fork this Repository
Click the "Fork" button in the top-right corner of this repository to create your own copy. This will allow you to make changes and push your work without affecting the original repository.

### 2. Clone Your Fork
Clone your forked repository to your local machine:
```bash
git clone https://github.com/YOUR_USERNAME/YOUR_FORKed_REPO.git
cd YOUR_FORKed_REPO
```

### 3. Set Up Your Environment
Follow the instructions in the root `README.md` (if available) or the specific module `README.md` files to set up your Python environment and dependencies.

**developed by sarah alowjan**
