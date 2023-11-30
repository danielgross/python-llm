## Overview
A very lightweight multiplexer for calling OpenAI, Anthropic, Mistral, etc all at once. It is a single file with minimal dependencies. 

```python
responses = asyncio.run(
    llm.complete(["What model are you?", "What is 2+2?"],
    models=['openai/gpt-3.5-turbo', 'replicate/mistral-7b', 'anthropic/claude-2'])
)
print(responses)
[
    {
        "prompt": "what model are you?",
        "responses": {
            "openai/gpt-3.5-turbo": "I am an AI language model created by OpenAI. Specifically, I am based on GPT-3 (Generative Pre-trained Transformer 3).",
            "replicate/mistral-7b": "I am Mistral, a large language model trained by Mistral AI.",
            "anthropic/claude-2": " I'm Claude, an AI assistant created by Anthropic."
        }
    }...
]
```


## Features
* Multiple Model Support: llm.py supports various models, including OpenAI's GPT-3.5, Replicate's Mistral, and Anthropic's Claude.
* Asynchronous Calls: The library leverages Python's asyncio for non-blocking calls to the LLMs.
* Concurrency Limiting: It includes a concurrency limiter to manage the number of simultaneous requests to the models.
* Caching Mechanism: Responses can be cached to optimize repeated requests, reducing the load and improving response time.
* Unified Interface: Provides a consistent interface to interact with different LLMs, simplifying the process of sending prompts and receiving responses.
* It's Just One File.

## Installation
It's Just One File. You'll need a .env file with the various API keys, either in your directory or in ~/.env globally. The kinds of things you'll need set are as so: 
```
REPLICATE_API_TOKEN=
OPENAI_API_KEY=
ANTHROPIC_API_KEY=
PPLX_API_KEY=
```
