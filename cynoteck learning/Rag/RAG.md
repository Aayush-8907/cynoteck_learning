RAG stands for **Retrieval-Augmented Generation**. In simple words, it combines two things:

1. **Retrieval**: Searching for the right information from documents or databases.
2. **Generation**: Using a language model (like ChatGPT or Claude) to answer a question based on that information.

The idea behind RAG is that language models don’t always give accurate answers because they don’t have the latest data. But with retrieval, we can provide the model with **real information** and **reduce mistakes**.

### Anthropic RAG

The main difference between Anthropic RAG and regular RAG is that in Anthropic RAG, after splitting the document into chunks, each chunk is sent to the LLM to generate a summary. This summary is then combined with the original chunk to create an embedding, which is stored in a vector database for similarity search.