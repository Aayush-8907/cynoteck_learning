- **Chains** in LangChain allow you to **combine multiple components (LLMs, prompts, tools, parsers, etc.) into a sequence or pipeline**.
- In traditional Python, you would manually pass the output of one function as the input to another.
- **LangChain Chains** automate this process—**you don't need to manage the flow manually**, and it handles input/output passing between steps for you.


the types of chains are

|**Chain Type**|**Use Case**|
|---|---|
|**SimpleChain**|Basic two-step processes (e.g., summarize → translate).|
|**SequentialChain**|Multi-step pipelines where each step passes output to the next.|
|**RouterChain**|Dynamic task routing (e.g., decide between summarization, sentiment analysis, or translation).|
|**ConversationalRetrievalChain**|Question-answering over documents with memory and context.|
|**TransformChain**|Apply custom Python logic to inputs or outputs between steps.|
