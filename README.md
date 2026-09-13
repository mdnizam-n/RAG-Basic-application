# 📄 PDF Q&A Assistant (RAG Application)

A lightweight Retrieval-Augmented Generation (RAG) web application built with **FastAPI** and containerized with **Docker**. Upload custom PDF documents, automatically process and index their content into a vector store, and ask contextual questions via an intuitive web interface.

---

## 🚀 Features

- **Document Ingestion:** Easy PDF upload and automated text parsing.
- **Smart Chunking & Embeddings:** Splits documents into semantically coherent chunks and indexes them in a vector store.
- **Context-Aware Q&A:** Answers queries accurately based strictly on uploaded document content using LangChain QA chains.
- **Dockerized Deployment:** Container-ready with standard non-root security practices for fast, consistent deployments.
- **Clean Web UI:** Straightforward frontend interface to interact with your knowledge base.

---

## 📁 Project Structure

```text
.
├── app.py               # FastAPI server and endpoint definitions
├── data_ingestion.py    # PDF loading and extraction logic
├── chunking.py          # Document splitting and chunking
├── embedding.py         # Vector embedding and storage
├── main.py              # LangChain QA retrieval chain definition
├── index.html           # Frontend user interface
├── static/              # CSS, JS, and UI static assets
├── Dockerfile           # Docker container configuration
├── requirements.txt     # Python dependencies
└── README.md            # Project documentation
```

---

## 🛠️ Tech Stack

- **Backend:** [FastAPI](https://fastapi.tiangolo.com/), [Uvicorn](https://www.uvicorn.org/)
- **LLM / RAG Pipeline:** [LangChain](https://www.langchain.com/)
- **Frontend:** HTML5, CSS3, JavaScript
- **Containerization:** [Docker](https://www.docker.com/)

---

## 🐳 Quickstart with Docker (Recommended)

### 1. Clone the Repository
```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### 2. Set Up Environment Variables (If Required)
If you use an external LLM API (such as OpenAI/HuggingFace), create a `.env` file in the root directory:
```env
OPENAI_API_KEY=your_actual_api_key_here
```

### 3. Build the Docker Image
```bash
docker build -t pdf-qa-assistant .
```

### 4. Run the Container
```bash
docker run -d -p 8000:8000 --name pdf-qa-app --env-file .env pdf-qa-assistant
```
*(If not using a `.env` file, simply omit `--env-file .env`)*

### 5. Access the Web App
Open your browser and navigate to:
```
http://localhost:8000
```

---

## 💻 Local Development (Without Docker)

### 1. Create a Virtual Environment
```bash
python -m venv venv
# Linux / macOS:
source venv/bin/activate
# Windows:
venv\Scripts\activate
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the Server
```bash
python app.py
```
Or run directly with Uvicorn:
```bash
uvicorn app:app --host 127.0.0.1 --port 8000 --reload
```

---

## 📌 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/` | Serves the web UI (`index.html`) |
| `POST` | `/upload` | Uploads and processes a PDF file into the vector store |
| `POST` | `/ask` | Queries the knowledge base with user questions |

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

---

