# AI Legal 6Document Assistant using RAG

An AI-powered **Legal Document Assistant** built using **Retrieval-Augmented Generation (RAG)** for intelligent legal PDF analysis and question answering.

## Overview

The system processes legal PDF documents by extracting text, splitting it into overlapping chunks, and generating **LegalBERT embeddings**. The embeddings are stored in **MongoDB** and retrieved using **cosine similarity**.

For a user query, the system retrieves the top relevant document chunks and passes them as context to **FLAN-T5** for context-grounded answer generation.

## Tech Stack

* **Python**
* **LegalBERT** – Domain-specific text embeddings
* **FLAN-T5** – Answer generation
* **Hugging Face Transformers**
* **PyTorch**
* **MongoDB**
* **Gradio**
* **PyPDF**
* **bcrypt**

## RAG Pipeline

```text
Legal PDF
   ↓
Text Extraction
   ↓
Chunking + Overlap
   ↓
LegalBERT Embeddings
   ↓
MongoDB Storage

User Query
   ↓
Query Embedding
   ↓
Cosine Similarity Search
   ↓
Top-K Relevant Chunks
   ↓
Context Augmentation
   ↓
FLAN-T5
   ↓
Generated Answer
```

## Features

* Legal PDF upload and processing
* Text extraction and chunking
* LegalBERT semantic embeddings
* Semantic retrieval using cosine similarity
* Retrieval-Augmented Generation
* Context-aware legal question answering
* Document summarization
* Source chunk retrieval
* User authentication with bcrypt
* MongoDB chat history

## Installation

```bash
pip install gradio pymongo pypdf bcrypt numpy python-dotenv transformers torch accelerate sentencepiece
```

Create a `.env` file:

```env
MONGO_URI=your_mongodb_connection_string
DB_NAME=legal
LEGAL_BERT_MODEL=nlpaueb/legal-bert-base-uncased
GENERATION_MODEL=google/flan-t5-base
```

Run:

```bash
python app.py
```

## Disclaimer

This project is intended for educational and informational purposes only. AI-generated responses should not be considered professional legal advice.
