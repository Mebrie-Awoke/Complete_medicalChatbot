# Complete Medical Chatbot

A Flask-based medical chatbot that uses Retrieval-Augmented Generation (RAG) with LangChain, ChromaDB, Groq, and Hugging Face embeddings to answer medical questions from PDF documents.

## 🚀 What this project does

- Loads medical PDF content from `data/`
- Splits documents into semantic chunks with LangChain
- Creates a persistent Chroma vector database in `chroma_db/`
- Uses `langchain_groq` for chat-based answer generation
- Serves a polished web chat interface via Flask

## ✅ Features

- Local ChromaDB vector store for fast semantic retrieval
- Hugging Face sentence-transformer embeddings
- PDF ingestion pipeline with chunking and metadata preservation
- Simple chat UI in `templates/chat.html`
- Dark/light theme toggle and quick question suggestions
- Easy deployment via Flask on port `8080`

## 📁 Project structure

- `app.py` — Flask app and chat endpoint
- `index.py` — build/rebuild the ChromaDB index from `data/`
- `src/helper.py` — PDF loading, document filtering, text splitting, and embeddings loader
- `src/prompt.py` — system prompt used to condition the chatbot
- `templates/chat.html` — front-end chat interface
- `static/style.css` — UI styling
- `chroma_db/` — persistent local vector store
- `data/` — place your input PDF files here

## 🛠️ Requirements

- Python 3.10 recommended
- `pip install -r requirements.txt`

## ⚙️ Setup

1. Clone the repository:

```bash
git clone https://github.com/Mebrie-Awoke/Complete_medicalChatbot.git
cd Complete_medicalChatbot
```

2. Create and activate a Python environment:

```bash
python -m venv venv
source venv/bin/activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Create a `.env` file in the project root with your Groq API key:

```ini
GROQ_API_KEY="your_groq_api_key"
```

> Note: The current app uses `langchain_groq` and local ChromaDB. `PINECONE_API_KEY` is not required for the current setup.

5. Add your medical PDF files to the `data/` directory.

6. Build the vector index:

```bash
python index.py
```

7. Start the Flask app:

```bash
python app.py
```

8. Open the chat interface in your browser:

```text
http://localhost:8080
```

## 💡 How it works

- `index.py` loads all PDFs in `data/`
- Documents are filtered and split into 500-token chunks with overlap
- `HuggingFaceEmbeddings` generates embeddings for each chunk
- ChromaDB stores the vectors persistently in `chroma_db/`
- `app.py` loads the DB and creates a retriever
- The user chat query triggers a retrieval step followed by generation from Groq

## 🧪 Notes

- If `chroma_db/` already exists, `app.py` will load it automatically
- If there is no existing database, run `python index.py` first
- The default Groq chat model is `llama-3.3-70b-versatile`
- This is a research/demo chatbot, not medical advice

## 🛠️ Troubleshooting

- `ModuleNotFoundError`: Ensure you installed dependencies from `requirements.txt`
- `No existing ChromaDB found`: Run `python index.py` to create the database
- `Invalid API key`: Confirm `GROQ_API_KEY` is set in `.env`

## 🙌 Credits

Built by Mebrie Awoke.

## 📌 License

This repository does not include a license file. Add one if you want to open source it.
 


