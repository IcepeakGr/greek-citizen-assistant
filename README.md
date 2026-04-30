# Greek Citizen Assistant

An AI-powered assistant that helps Greek citizens navigate government procedures using RAG (Retrieval-Augmented Generation) with a Greek-optimized LLM.

## Problem

Greek citizens struggle to find accurate information about government procedures. Information is scattered across multiple ministry websites.

This assistant solves that - ask a question in Greek, get an answer with sources.

## Tech Stack

- **LLM**: Ollama + OpenEuroLLM-Greek (runs locally, free)
- **Vector DB**: ChromaDB for document search
- **API**: FastAPI with automatic documentation
- **Container**: Docker
- **CI/CD**: GitHub Actions

## Quick Start

### Prerequisites
- Python 3.11+
- [Ollama](https://ollama.com) installed
- Git

### Installation

```bash
# Clone repo
git clone https://github.com/YOUR_USERNAME/greek-citizen-assistant.git
cd greek-citizen-assistant

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Pull Greek model
ollama pull jobautomation/OpenEuroLLM-Greek
ollama pull nomic-embed-text

# Load documents
python scripts/load_documents.py

# Run API
uvicorn src.api.main:app --reload