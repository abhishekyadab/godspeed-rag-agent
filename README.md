# Assignment Features & Usage Guide

This project is a Retrieval-Augmented Generation (RAG) agent for the Godspeed framework documentation.  
It meets all assignment requirements, including vector DB integration, flexible input, query API, and multimodal readiness.

---

## Features Explained

### 1. **Retrieval-Augmented Generation (RAG) Agent**
- The agent can answer technical questions about the Godspeed framework by searching and understanding the official documentation.
- It uses Google Gemini for embeddings and answer generation.

### 2. **Vector Database Integration**
- All documentation files (Markdown, YAML, code, etc.) are embedded and stored in a local vector database (ChromaDB).
- This allows for fast, semantic search and retrieval of relevant information.

### 3. **Flexible Input (Upsert)**
- You can update the knowledge base by:
  - Pointing to a GitHub repo/branch (by changing the `repo_path` in the code).
  - (Optionally) Uploading documentation files via an API (see code comments for how to extend with FastAPI).
- This ensures your RAG agent always uses the latest documentation.

### 4. **Query API / Interactive Querying**
- The agent supports interactive CLI querying out of the box.
- You can extend it to a REST API for programmatic access (see code comments for FastAPI example).

### 5. **Multimodal Ready**
- The system is built to handle text and code.
- It can be extended to support images or diagrams using Gemini’s multimodal capabilities (if needed).

---

## How to Run (Step-by-Step)

### **Step 1: Clone the Repositories**
- Clone this RAG agent project and the [Godspeed documentation repo](https://github.com/godspeedsystems/gs-documentation).

### **Step 2: Install Dependencies**
- This installs all required Python packages (ChromaDB, LangChain, Gemini, etc.).

### **Step 3: Set Up Your API Key**
- Create a `.env` file in your project folder and add your Gemini API key:

### **Step 4: Prepare the Documentation**
- Make sure the Godspeed documentation is in a folder next to your project (e.g., `../gs-documentation`).

### **Step 5: Run the Agent**
- The first run will process and embed all documentation files (this may take several minutes).

### **Step 6: Ask Questions**
- When prompted, type your question (e.g., “How to enable JWT authentication?”).
- The agent will search the docs and return the most relevant answer, including code/config examples when available.

---

## Special Notes & Limitations

- **First run may be slow:** Embedding all docs can take 5–15 minutes.
- **API endpoints for ingestion/querying:** The CLI is ready; REST API can be added using FastAPI (see code comments).
- **Multimodal support:** The code is ready for text/code; image support can be added if needed.
- **Keep docs updated:** If the Godspeed docs change, re-run the agent to refresh the knowledge base.
- **Best for technical/configuration questions:** Works best for questions covered in the official documentation.

---

## Example Queries

- How to enable JWT authentication?
- How to install plugins in Godspeed?
- How to create a datasource plugin?
- Show an example http.yaml configuration.



