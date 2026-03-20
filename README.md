# 🤖 Real-Time AI Assistant using RAG + LangChain

A locally-run, real-time AI assistant that answers questions by searching the web — powered by **Llama 3**, **LangChain**, and **DuckDuckGo Search**. No paid APIs. No cloud dependency. Runs entirely on your machine.

---

## 🧠 How It Works

This project implements **Retrieval-Augmented Generation (RAG)** with a real-time twist:

1. You ask a question
2. DuckDuckGo searches the web for relevant results
3. The results are injected as context into a prompt
4. Llama 3 (running locally via Ollama) answers based *only* on those results

This means the assistant isn't limited to its training data — it can answer questions about current events in real time.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| [Ollama](https://ollama.com/) | Runs Llama 3 locally |
| [LangChain](https://www.langchain.com/) | Orchestrates the RAG pipeline |
| [DuckDuckGo Search](https://pypi.org/project/duckduckgo-search/) | Free, no-API-key web search |
| Python 3.8+ | Core language |

---

## ⚙️ Setup & Installation

### 1. Install Ollama

**Windows (PowerShell):**
```powershell
irm https://ollama.com/install.ps1 | iex
```

**Mac/Linux:**
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

### 2. Pull the Llama 3 Model (one-time only)

```bash
ollama pull llama3:8b
```

> This downloads ~4GB. You only need to do this once — the model is stored locally.

### 3. Install Python Dependencies

```bash
pip install langchain langchain_community langchain_ollama ddgs
```

---

## 🚀 Running the Assistant

Make sure Ollama is running (check your system tray or run `ollama serve`), then:

```bash
python assistant.py
```

Or if using the Jupyter Notebook, simply run all cells.

**Example interaction:**
```
🤖 Hello! I'm a real-time AI assistant. What's new?
You: What are the latest developments in AI?
🤖 Thinking...
🤖: Based on the search results...
```

Type `exit` or `quit` to stop.

---

## 📁 Project Structure

```
realtime-ai-assistant/
│
├── assistant.py        # Main script
├── assistant.ipynb     # Jupyter Notebook version
├── requirements.txt    # Python dependencies
└── README.md
```

---

## 📋 Requirements

- Python 3.8+
- Ollama installed and running
- `llama3:8b` model pulled via Ollama
- Internet connection (for DuckDuckGo searches)

---

## 💡 Key Concept: Why RAG?

Standard LLMs are frozen at their training cutoff — they don't know what happened last week. RAG (Retrieval-Augmented Generation) solves this by fetching fresh, real-world data at query time and grounding the LLM's response in that data. The result is an assistant that is both intelligent *and* up-to-date.

---

## 🔮 Possible Extensions

- Swap DuckDuckGo for a **vector database** (e.g. ChromaDB) to query your own documents
- Add a **Streamlit** frontend for a chat UI
- Swap Llama 3 for other local models like **Mistral** or **Phi-3**

---

## 📄 License

MIT License — free to use and modify.
