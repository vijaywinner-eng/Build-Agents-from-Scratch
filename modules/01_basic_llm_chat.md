

### 1. Prompts

A **prompt** is just text you send to the model. It can be a question like "What is an AI agent?", an instruction like "Explain quantum computing", or a request like "Write a poem about the ocean". The model completes or responds to this text based on patterns it learned during training.

### 2. Tokens

Models don't see text as words - they see **tokens**. Tokens are pieces of text (often words or subwords). For example, "Hello world" might be 2 tokens, while "artificial intelligence" could be 2-4 tokens depending on the model.

This matters because models have token limits (context windows), generation is measured in tokens per second, and longer prompts use more tokens, leaving less room for responses.

### 3. Context

The **context** is everything the model can "see" at once. It includes your prompt, any previous conversation, and system instructions. Models have a **context window** (e.g., 2048 tokens). If you exceed it, the model can't see the earlier text.

## The Code

Look at `agent/agent.py`, see `simple_generate()` method:

```python
def simple_generate(self, user_input: str) -> str:
    """
    Simplest possible interaction - just pass text to the LLM.
    """
    return self.llm.generate(user_input)
```

That's it. One line. No complexity.

## How to Run

Look at `complete_example.py`, see `01_basic_chat()` method:

```python
from agent.agent import Agent

agent = Agent("models/llama-3-8b-instruct.gguf")

response = agent.simple_generate("What is an AI agent?")
print(response)
```