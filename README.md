# Local AI Agent with RAG

A local AI-powered question-answering system for restaurant reviews using Retrieval-Augmented Generation (RAG). This project uses LangChain, Ollama, and ChromaDB to create an intelligent agent that can answer questions about a pizza restaurant based on customer reviews.

## Features

- **Local LLM**: Uses Ollama with Llama 3 model for natural language processing
- **RAG Implementation**: Retrieves relevant reviews before generating answers
- **Vector Database**: ChromaDB for efficient similarity search
- **Embeddings**: Uses mxbai-embed-large model for document embeddings
- **Interactive CLI**: Command-line interface for asking questions

## Prerequisites

- Python 3.8+
- [Ollama](https://ollama.ai/) installed locally
- Ollama models downloaded:
  - `llama3`
  - `mxbai-embed-large`

## Installation

1. Clone this repository:
```bash
git clone https://github.com/Indrajit-sarkar/Local-AI-Agent-With-RAG.git
cd Local-AI-Agent-With-RAG
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Install Ollama models:
```bash
ollama pull llama3
ollama pull mxbai-embed-large
```

## Usage

Run the main script:
```bash
python main.py
```

Ask questions about the pizza restaurant based on the reviews. Type 'q' to quit.

Example questions:
- "What do customers say about the pizza quality?"
- "How is the service?"
- "What are the most common complaints?"

## Project Structure

- `main.py` - Main application with interactive Q&A loop
- `vector.py` - Vector database setup and retriever configuration
- `realistic_restaurant_reviews.csv` - Restaurant reviews dataset
- `chroma_langchain_db/` - ChromaDB storage (generated on first run)

## How It Works

1. Restaurant reviews are loaded from CSV and converted to vector embeddings
2. Embeddings are stored in ChromaDB for efficient retrieval
3. User asks a question
4. System retrieves the 5 most relevant reviews using similarity search
5. Retrieved reviews are passed to the LLM with the question
6. LLM generates an answer based on the context

## License

MIT License
