# 🧠 PDF Chatbot with RAG, FAISS & LLaMA (LangChain)

This project is an interactive PDF-based chatbot built using:

- 🧠 **RAG** (Retrieval-Augmented Generation)
- 🧮 **FAISS** for vector similarity search
- 🧾 **LangChain** for chaining LLM responses
- 🤖 **Ollama (LLaMA/Mistral)** as the backend LLM
- ⚡ **Streamlit** frontend for user interaction

---

## 📂 Project Structure

```
RAG/
├── pdf_chatbot/
│   ├── app.py              # Main Streamlit app
│   ├── faiss_index/        # Saved FAISS vector store
│   └── uploaded/           # Uploaded PDFs
├── scraping/
│   └── scraper.py          # Additional scraping logic
└── scripting/              # (Optional) other scripts
```

---

## 🚀 Features

- Upload a PDF and ask questions about its content.
- Automatically splits text and generates vector embeddings.
- Retrieves context-relevant chunks using FAISS.
- Uses a local LLM (Mistral via Ollama) to generate accurate responses.

---

## 🛠️ Installation

1. **Clone the repo:**
   ```bash
   git clone https://github.com/your-username/rag-pdf-chatbot.git
   cd rag-pdf-chatbot
   ```

2. **Create a virtual environment (optional):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Start the Streamlit app:**
   ```bash
   cd pdf_chatbot
   streamlit run app.py
   ```

> ⚠️ Make sure [Ollama](https://ollama.com/) is installed and running with the `mistral` model:
```bash
ollama run mistral
```

---

## 🧠 How It Works

1. User uploads a PDF.
2. Text is extracted and split into chunks.
3. Chunks are embedded using a sentence transformer model.
4. FAISS indexes and stores these embeddings.
5. When a question is asked:
   - Relevant chunks are retrieved based on vector similarity.
   - The LLM is prompted with those chunks to generate an answer.

---

## ✅ Requirements

- Python 3.8+
- [Ollama](https://ollama.com/)
- Streamlit
- LangChain
- FAISS
- PyPDF2
- sentence-transformers
