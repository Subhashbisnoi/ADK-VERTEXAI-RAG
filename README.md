# 🧠 Vertex AI RAG Agent using Google's ADK

This project defines a **Retrieval-Augmented Generation (RAG) Agent** using **Google's Agent Developer Kit (ADK)**. The agent is designed to run directly on the **ADK Web UI** and can interact with **Vertex AI** to manage and query document corpora.

---

## 🌟 Overview

Using ADK, you can build powerful agents that combine large language models with tool-based interactions. This agent enables:
- Document-based Q&A using Retrieval Augmented Generation (RAG)
- Management of corpora and documents in Vertex AI
- Easy interaction with GCS/Google Drive documents

---

## ⚙️ Features

This RAG agent supports the following capabilities:
- 🔍 **Query documents** using RAG from a selected corpus
- 📚 **List all corpora** available in the Vertex AI environment
- 📦 **Create a new corpus** for document storage and retrieval
- 📄 **Add data/documents** to a corpus from GDrive or GCS
- ℹ️ **Get information** about an existing corpus (document stats, file info)
- 🧹 **Delete a document** from a corpus
- 🗑️ **Delete an entire corpus** when it's no longer needed

---

## 🗂️ Project Structure

```text
ADK-VERTEXAI-RAG/
├── .venv/                     # (Optional) Python virtual environment
├── rag_agent/                 # Main RAG Agent package
│   ├── agent.py               # ADK agent definition and core instruction set
│   ├── __init__.py
│   ├── tools/                 # Individual tool implementations
│   │   ├── __init__.py
│   │   ├── add_data.py        # Tool to add documents to a corpus
│   │   ├── create_corpus.py   # Tool to create a new corpus
│   │   ├── delete_corpus.py   # Tool to delete a corpus
│   │   ├── delete_document.py # Tool to delete specific documents
│   │   ├── get_corpus_info.py # Tool to get corpus metadata
│   │   ├── list_corpora.py    # Tool to list all corpora
│   │   ├── rag_query.py       # Tool to run RAG queries
│   │   └── utils.py           # Shared helper functions
├── config.py                  # Configuration and helper logic
├── .env                       # (Optional) Environment variables like credentials
├── requirements.txt           # Project dependencies
├── evalsetcfaf5a.evals...     # Evaluation set (if used for testing)
└── README.md                  # Project documentation
```

---

## 🚀 How to Run (via ADK Web UI)

> This project is designed to run **on the web-based interface of Google’s Agent Developer Kit (ADK)**, not as a standalone Python script.

### Steps:
1. Go to [Google Vertex AI > Agents](https://console.cloud.google.com/vertex-ai/agents).
2. Click **"Create Agent"** > Select **"Upload from code"**.
3. Upload the folder that contains your `rag_agent` directory (not just the inner files).
4. The system will detect the `root_agent` object from `agent.py`.
5. Use the ADK Web UI to:
   - Add tools
   - Run queries
   - View logs
   - Test your RAG workflows

---

## 🛠️ Tool Descriptions

| Tool Name           | Purpose                                                      |
|---------------------|--------------------------------------------------------------|
| `rag_query`         | Run a retrieval-augmented query on a specified corpus        |
| `list_corpora`      | List all available corpora                                   |
| `create_corpus`     | Create a new document corpus                                 |
| `add_data`          | Add documents (Google Drive/GCS) to a specific corpus        |
| `get_corpus_info`   | View metadata (file names, stats) of a corpus                |
| `delete_document`   | Delete a specific document from a corpus                     |
| `delete_corpus`     | Delete an entire corpus and all documents within it          |

---

## 💻 Local Development (Optional)

You may want to set up a local dev environment to edit or test tools before uploading:

```bash
# Clone the repository
git clone https://github.com/Subhashbisnoi/vertexai-rag-agent.git
cd vertexai-rag-agent

# Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

---

## 🔐 Environment Variables

If you need to authenticate locally, create a `.env` file with the following:

```env
GOOGLE_APPLICATION_CREDENTIALS=path/to/your-service-account.json
```

But this is not required when running inside the ADK Web UI.

---

## 🤝 Contributions

Pull requests and ideas are welcome! This project aims to help others build custom RAG-based solutions on Google Cloud using ADK.

---

## 🔗 References

- [Google ADK Overview](https://cloud.google.com/vertex-ai/docs/agents/overview)
- [Vertex AI RAG Documentation](https://cloud.google.com/vertex-ai/docs/generative-ai/agents/use-retrieval)
