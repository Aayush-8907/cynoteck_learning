- **Stateless**: LLMs process each user query **independently** without knowing what was asked previously.
- **No Built-in Context**: If you ask a follow-up question, the LLM won’t remember the earlier conversation unless you provide the previous context again.

### **Example:**

**User:** Who is Neymar?  
**LLM Response:** Neymar is a Brazilian football player.

**User:** What is his current club?

- The LLM won’t know who “his” refers to unless you repeat the context: _“What is Neymar’s current club?”


### **Types of Memory in LangChain**

1. **Conversation Buffer Memory**
    
    - **What it does**: Stores the **entire conversation history** and passes it to the LLM with each request.
    - **Use Case**: Best for short conversations where retaining full context is essential.
    - **Example**: Customer support chatbots.
2. **Conversation Buffer Window Memory**
    
    - **What it does**: Stores only the **last `n` interactions** (a sliding window of recent conversations).
    - **Use Case**: Ideal for long conversations where full history is unnecessary, but recent context is important.
    - **Example**: Chatbots that need to remember only the last 5–10 questions.
3. **Conversation Summary Memory**
    
    - **What it does**: Summarizes the conversation into a **compact summary** and uses that for context instead of the full chat history.
    - **Use Case**: Useful for **long, multi-turn conversations** without exceeding the context window of the LLM.
    - **Example**: Personal assistants that need to remember key points from a long conversation.
4. **Custom Memory**
    
    - **What it does**: Allows you to **define and store specific pieces of information**, such as user preferences, personal details, or extracted facts.
    - **Use Case**: For applications that require **persistent, structured memory** of user-specific data.
    - **Example**: Personalization—remembering a user's name, favorite color, or preferences across sessions.

---

### **Example Use Case for Each Memory Type**

1. **Buffer Memory**: Simple FAQ chatbot that remembers the entire conversation.
2. **Buffer Window Memory**: AI tutor that remembers only the last 5 questions.
3. **Summary Memory**: Virtual assistant that gives a summary of past discussions.
4. **Custom Memory**: Health assistant that remembers the user's medical history and personal data.