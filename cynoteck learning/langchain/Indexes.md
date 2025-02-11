In **LangChain**, **indexes** are used to **connect external knowledge sources (PDFs, documents, databases, etc.) with the LLM**, enabling it to retrieve relevant information when answering user queries.

### **Types of Indexes in LangChain**

1. **Vector Index (Embedding-based Search)**
    
    - Converts documents into vectors and stores them in a vector database (e.g., **FAISS**, **Pinecone**, **Weaviate**).
    - Useful for **semantic search**—the LLM retrieves relevant chunks based on similarity.
    
    **Example:**
    
    - Input: _“Tell me about Brazil’s top football players.”_
    - The vector index retrieves document chunks related to Brazilian football players.
2. **Text Splitters + Simple Keyword Search**
    
    - Splits large documents into smaller chunks and stores them for **simple keyword-based retrieval**.
3. **ConversationalRetrievalChain** (Document-QA)
    
    - Maintains context across multiple queries, acting like a **chatbot over documents**.