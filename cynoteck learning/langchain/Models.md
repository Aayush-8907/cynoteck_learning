
It's contains the list of model that are used for interacting with the user. 

### Why we use langchain model

 LangChain provides a unified interface for working with various language models (e.g., OpenAI, Claude, Cohere). Instead of writing separate code for each model, LangChain abstracts away the differences. You only need to change the model's configuration (like the package name or API key), while the rest of the code remains the same. This makes it easier to switch between models without significant code changes.

### Example: 
```from langchain import OpenAI, ChatAnthropic

# OpenAI 
model llm = OpenAI(model="text-davinci-003", api_key="your_openai_api_key") 

# Switching to Claude (Anthropic model) 
llm = ChatAnthropic(model="claude-v1", api_key="your_anthropic_api_key")

response = llm("Explain LangChain") print(response)
```


## Langchain contains two model

- **Language Model** -The user sends text as input, and the output is typically **text**. The model performs tasks like text generation, summarization, question-answering, etc.

- **Embedding Model**: The user sends text as input, and the output is a **vector (numerical representation)**. This vector represents the meaning of the text in a multi-dimensional space, useful for tasks like similarity search, clustering, and classification.