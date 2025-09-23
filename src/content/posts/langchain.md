---
title: Using Langchain to Call Remote APIs with JSON Response Format
published: 2025-09-23
description: 'Learn how to use Langchain to call remote APIs and generate structured JSON responses'
image: ''
tags: [Langchain, API, JSON]
category: 'AI'
draft: false
lang: 'en'
---

# Calling Remote APIs with Langchain and Structured JSON Responses

This guide demonstrates how to use Langchain to call remote APIs and generate structured JSON responses, following an OpenAI-style approach.

## Implementation Example

```python
import os
from langchain_openai import ChatOpenAI
import json
from langchain_core.prompts import ChatPromptTemplate

# Define the prompt template with system and human messages
prompt = ChatPromptTemplate.from_messages(
    [
        (
            "system",
            "{role}",
        ),
        ("human", "{input}"),
    ]
)

# Initialize the language model with specific configurations
llm = ChatOpenAI(
    model="doubao-seed-1-6-250615",
    api_key=os.getenv("OPENAI_API_KEY"),
    base_url="https://ark.cn-beijing.volces.com/api/v3"
).bind(response_format={"type": "json_object"})

# Create the processing chain
chain = prompt | llm

# Execute the chain with specific inputs
resp = chain.invoke({
    "role": "You are a device classifier", 
    "input": task
})

# Parse and print the JSON response
print(json.loads(resp.content))
```

## Key Components Explained

1. **Prompt Template**: Uses `ChatPromptTemplate` to structure the conversation with system and human roles
2. **Language Model**: Configured with a specific model and API endpoint
3. **Response Format**: Binds the model to return JSON objects for structured output
4. **Chain**: Combines the prompt and model into a callable processing chain
5. **Execution**: Invokes the chain with role and input parameters

This approach allows for consistent, structured responses from remote AI services.
