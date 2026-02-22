# TDSE-LAB04-RAGandBasicLLM

Introduction to RAG (Retrieval-Augmented Generation) systems and LLM Agents using Google Gemini and LangChain.

## 📋 Table of Contents
- [Project Description](#project-description)
- [Setup](#setup)
- [API Keys Required](#api-keys-required)
- [How to Run the Notebooks](#how-to-run-the-notebooks)

---

## Project Description

This repository contains two Jupyter notebooks demonstrating different AI agent implementations using LangChain and Google Gemini.

### Notebook 1: basicLangChainLLM.ipynb
**Conversational AI Agent with Custom Tools**

This notebook demonstrates how to build an intelligent agent that can:
- **Use custom tools**: The agent has access to two functions - one to get user location based on their ID, and another to retrieve weather information for a specific city
- **Make decisions**: The agent automatically determines which tools to use based on the user's question
- **Maintain conversation memory**: Remembers previous interactions within a session using checkpointers

**Example:**
User asks: "What's the weather outside?" → Agent retrieves user location → Gets weather for that location → Responds with a pun-based answer

### Notebook 2: ragProject.ipynb
**RAG (Retrieval-Augmented Generation) System**

This notebook builds a complete RAG pipeline that enables the AI to answer questions based on external knowledge:
- **Document ingestion**: Loads a blog post from the web about LLM agents
- **Text processing**: Splits the long document into smaller chunks for better retrieval
- **Embedding creation**: Converts text chunks into numerical vectors using Google's embedding model
- **Vector storage**: Stores embeddings in Pinecone, a vector database optimized for similarity search
- **Semantic retrieval**: When you ask a question, the system finds the most relevant document chunks based on meaning, not just keywords
- **Context-aware responses**: The agent uses retrieved information to provide accurate answers grounded in the source document

**Example:**
User asks: "What is task decomposition?" → System searches vector database for relevant chunks → Retrieves most similar content → Agent reads context and generates informed answer citing the source

**Technologies:**
- **LangChain**: Framework for orchestrating LLM agents and tools
- **Google Gemini 2.5 Flash Lite**: Language model for understanding and generation
- **Pinecone**: Vector database for semantic search in RAG system

---

## Setup

### Running in Google Colab
1. Upload the notebook to Google Colab
2. Run cells in order from top to bottom
3. Enter API keys when prompted

### Running in Visual Studio Code
1. Create a Python virtual environment
2. Install Jupyter
3. Open the notebook in VS Code
4. Select the virtual environment as kernel
5. Run cells in order from top to bottom

---

## API Keys Required

You will need to obtain the following API keys before running the notebooks:

### Google AI Studio (Required for both notebooks)
- **Used for:** Gemini language model and embeddings

### Pinecone (Required only for RAG notebook)
- **Get it here:** https://app.pinecone.io/
- **Used for:** Vector storage and semantic search

---

## How to Run the Notebooks

### General Instructions

1. **Open the notebook** (either `basicLangChainLLM.ipynb` or `ragProject.ipynb`)

2. **Execute cells sequentially** from top to bottom

3. **Enter API keys when prompted:**
   - During execution, you'll see prompts like: `Enter your GOOGLE API key:`
   - Paste your API key and press Enter
   - **When to enter keys:**
     - **basicLangChainLLM.ipynb:** Cell 3 asks for Google API key
     - **ragProject.ipynb:** Cell 3 asks for Google API key, Cell 5 asks for Pinecone API key

4. **Dependencies are installed automatically**
   - The first cell of each notebook installs required packages
   - No manual installation needed

---

## Architecture

### basicLangChainLLM.ipynb
```
User Query → Agent (Gemini) → Custom Tools → Structured Response
```

### ragProject.ipynb
```
Web Document → Text Splitting → Embeddings → Pinecone → Similarity Search → Agent Response
```
---

## Acknowledgments

- [LangChain Documentation](https://python.langchain.com/docs/get_started/introduction)
- [Google Gemini API](https://ai.google.dev/docs)
- [Pinecone Documentation](https://docs.pinecone.io/)

---

## Author

**Juan Sebastian Puentes Julio**
