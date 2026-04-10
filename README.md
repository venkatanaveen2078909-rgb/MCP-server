# AI MCP System

An intelligent, Model Context Protocol (MCP) compatible Retrieval-Augmented Generation (RAG) backend utilizing LangGraph and FastAPI.

This system allows seamless chaining of AI model logic (powered by Groq APIs) and document context search abilities via HuggingFace embedding configurations and a FAISS local vector database.

---

## 🚀 Features

* **ReAct Agent Flow Setup:** Custom autonomous routing utilizing LangGraph state machines.
* **Dynamic RAG Pipeline:** Secure and optimized ingestion, chunking, and semantic vector searching.
* **Persisted Thread Memory:** SQLite integrated transactions storing continuous session context tracking.
* **Fully Modular Architecture:** Easily scalable with new LangGraph agents and standalone MCP wrappers.
* **Container Ready:** Ships with explicit configurations targeting lightweight reproducible Python Docker builds.

---

## 📋 Prerequisites

Before running the backend, make sure you have installed:

* Python 3.11+
* Create a Groq API Key: https://console.groq.com/keys

---

## 🛠️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/venkatanaveen2078909-rgb/MCP-server.git
cd MCP-server
```

### 2. Activate a local Virtual Environment (Recommended)

```bash
# On Windows
python -m venv venv
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Create Environment Variables

Create a `.env` file inside the root directory:

```env
GROQ_API_KEY=your_groq_api_key_here
```

### 5. Start the Application

```bash
uvicorn main:app --reload
```

The server will now be live at:
👉 http://127.0.0.1:8000

> ⏳ Note: On first startup, it may take ~60 seconds to download HuggingFace embedding models (~80MB).

---

## 🔌 API Usage (Swagger UI)

Access the interactive API docs:
👉 http://127.0.0.1:8000/docs

### Available Endpoints

* `GET /` → Server health check
* `POST /api/chat/chat` → Send input to ReAct agent (Groq + RAG context)
* `POST /api/rag/query` → Query FAISS vector database

---

## 🐳 Docker

Build and run the backend using Docker:

```bash
docker build -t ai-mcp-system .
docker run -p 8000:8000 ai-mcp-system
```

---

## 📌 Notes

* Ensure `.env` is correctly configured before running.
* First-time setup requires internet for model downloads.
* Easily extendable with additional LangGraph agents and MCP integrations.
