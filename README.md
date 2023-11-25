## Overview
llm.py a very lightweight multiplexer for calling OpenAI, Anthropic, Mistral, etc all at once. It is a single file with minimal dependencies. 

## Features
* Multiple Model Support: llm.py supports various models, including OpenAI's GPT-3.5, Replicate's Mistral, and Anthropic's Claude.
* Asynchronous Calls: The library leverages Python's asyncio for non-blocking calls to the LLMs.
* Concurrency Limiting: It includes a concurrency limiter to manage the number of simultaneous requests to the models.
* Caching Mechanism: Responses can be cached to optimize repeated requests, reducing the load and improving response time.
* Unified Interface: Provides a consistent interface to interact with different LLMs, simplifying the process of sending prompts and receiving responses.
* It's Just One File.

## Installation
It's Just One File.

## Usage
```python
responses = asyncio.run(
    llm.complete(["What is the capital of France?"], models=['openai/gpt-3.5-turbo', 'replicate/mistral-7b'])
)```

Handling Responses:
The responses are returned in a structured format, in the order you sent them.