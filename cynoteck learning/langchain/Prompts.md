- A **prompt** is the input text you provide to an LLM to guide its response. 
- **All interactions** with an LLM are done using prompts. 
- The **quality and clarity** of the prompt directly affect the output from the model.


# The template provide by the langchain

#### 1. Basic Prompt Template (`PromptTemplate`)

#### Use Case: 
For simple text generation with dynamic inputs.

#### **Description**: 
This template formats a prompt by replacing placeholders with user-defined values.

**Example**:

```
from langchain import PromptTemplate

template = "Translate the following text to French: {text}"
prompt = PromptTemplate(input_variables=["text"], template=template)

formatted_prompt = prompt.format(text="How are you?")
print(formatted_prompt)

```

#### 2. **Few-Shot Prompt Template (`FewShotPromptTemplate`)**

#### Use Case: 
When you want to provide examples to guide the model’s response. This improves accuracy for complex tasks.

#### Description: 
You supply multiple examples in the prompt to help the model learn the pattern or style.

**Example**:

```
from langchain import FewShotPromptTemplate

examples = [
    {"question": "What is 2 + 2?", "answer": "4"},
    {"question": "What is 3 + 5?", "answer": "8"}
]

example_prompt = PromptTemplate(input_variables=["question"], template="Q: {question}\nA: {answer}")

few_shot_prompt = FewShotPromptTemplate(
    examples=examples,
    example_prompt=example_prompt,
    prefix="Answer the following math questions:",
    suffix="Q: {question}\nA:",
    input_variables=["question"]
)

formatted_prompt = few_shot_prompt.format(question="What is 10 + 15?")
print(formatted_prompt)

```

#### 3. **Chat Prompt Template (`ChatPromptTemplate`)**

#### Use Case: 
For chat-based models (like OpenAI's `gpt-4` or `gpt-3.5-turbo`) that use a conversation format.

#### Description: 
Helps create structured multi-turn conversations by defining roles (`system`, `user`, `assistant`).

**Example**:

```
from langchain import ChatPromptTemplate, SystemMessagePromptTemplate, HumanMessagePromptTemplate

system_template = "You are a helpful assistant."
human_template = "Translate '{text}' to Spanish."

system_message = SystemMessagePromptTemplate.from_template(system_template)
human_message = HumanMessagePromptTemplate.from_template(human_template)

chat_prompt = ChatPromptTemplate.from_messages([system_message, human_message])

formatted_prompt = chat_prompt.format(text="How are you?")
print(formatted_prompt)

```

#### 4. **Output Parsers (`StructuredOutputParser`)**

#### Use Case:
When you need a specific response format (e.g., JSON, list, or structured data).

#### Description: 
Ensures the model returns data in a structured format for easier parsing.

**Example**:

```
from langchain.output_parsers import StructuredOutputParser, ResponseSchema

response_schemas = [
    ResponseSchema(name="name", description="The person's name"),
    ResponseSchema(name="age", description="The person's age")
]

output_parser = StructuredOutputParser.from_response_schemas(response_schemas)
prompt = output_parser.get_format_instructions()

print(prompt)

```


### When to Use Each Type:

|**Type**|**Use Case**|
|---|---|
|**`PromptTemplate`**|Simple text generation with placeholders.|
|**`FewShotPromptTemplate`**|Tasks requiring examples to improve accuracy (math questions, coding tasks, etc.).|
|**`ChatPromptTemplate`**|Chat-based interactions with role-based messages (`system`, `user`, `assistant`).|
|**`StructuredOutputParser`**|When you need structured outputs (e.g., JSON) for easy post-processing.|