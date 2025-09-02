# 🧩 LangChain Mini-RAG

A **Retrieval-Augmented Generation (RAG)** prototype built with [LangChain](https://python.langchain.com/).
This project demonstrates how to load documents, split them into chunks, embed them, and perform semantic retrieval with a vector store (Chroma).

---

## ✅ Features

* Load documents from **PDF** and **DOCX** formats
* Chunk text into overlapping segments (`chunk_size=1000`, `overlap=200`)
* Generate embeddings using **OpenAI’s text-embedding-3-small**
* Store embeddings in a **Chroma** vector database (`chroma_db/`)
* Perform **similarity search** with retriever interface (`k=3`)
* Run demo queries directly inside the notebook

---

## 📂 Repository Structure

```
langchain-mini-rag/
├── .git/                       # Git repo metadata
├── chroma_db/                  # Persisted Chroma vector database
├── dataset/                    # Input dataset (PDF/DOCX files go here)
├── project_instruction/         # Project instructions & requirements
├── langchain-mini-rag.ipynb    # Main Jupyter Notebook (Mini-RAG pipeline)
└── README.md                   # Documentation
```

---

## 📝 Example Query

Inside the notebook, a sample retriever call is already included:

```python
result = retriever.invoke("what is headquaters of the greenland")
print(result)
```

**Expected output:**

```
Loaded 5 documents from dataset/
Split documents into 48 chunks
Created embeddings for 48 document chunks
Vector store created and persisted to './chroma_db'

[Document(page_content="Greenland’s headquarters is located in...", metadata={...}), ...]
```

---

## 📖 Resources

* [LangChain Documentation](https://python.langchain.com/docs/introduction/)
* [Chroma Vector Store Integration](https://python.langchain.com/docs/integrations/vectorstores/chroma/)
* [OpenAI Embeddings Guide](https://platform.openai.com/docs/guides/embeddings)

---

## ✅ Next Steps

* Add support for `.txt` and `.md` files in dataset
* Expose retrieval as a **CLI tool** or **Streamlit app**
* Use HuggingFace embeddings (no API key required)
* Connect an LLM to answer queries from retrieved chunks

---

💡 This repo is a **starter template for retrieval-based AI applications** with LangChain. You can extend it into a chatbot, knowledge base assistant, or document Q\&A system.