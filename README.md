# LLM Conversation Workbench

A Python-based workbench for building and experimenting with LLM-powered conversational applications using Google's Gemini API and the `google-genai` SDK.

## Overview

This repository provides a practical foundation for working with large language models through Python. It currently demonstrates authenticated Gemini API requests, model configuration, response handling, and structured error management.

The project is designed to grow into a broader workspace for single-turn prompts, multi-chat conversations, tool calling, and other conversational AI workflows.

## Current Features

- Gemini API integration with the modern `google-genai` SDK
- Secure API key loading through environment variables
- Single-turn text generation
- Gemini response object handling
- Model selection and configuration
- Automatic Function Calling configuration
- Authentication, rate-limit, server, and network error handling
- Jupyter Notebook-based experimentation

## Project Structure

```text
.
├── LLM_Chat_Basics.ipynb
├── README.md
└── .gitignore
```

## Requirements

- Python 3.10 or later
- A Google Gemini API key
- Jupyter Notebook or Visual Studio Code with the Jupyter extension

## Installation

Install the required packages:

```bash
pip install google-genai python-dotenv
```

## Configuration

Create a local file named `llm_api_variables.env` in the project directory:

```env
GEMINI_API_KEY=your_api_key_here
```

The environment file is excluded from version control. Never commit API keys or other credentials to the repository.

## Usage

Open `LLM_Chat_Basics.ipynb` and run the cells in order. The notebook demonstrates how to:

1. Load the Gemini API key securely.
2. Create an authenticated GenAI client.
3. Send a prompt to a Gemini model.
4. Receive a `GenerateContentResponse` object.
5. Extract and display the generated text.
6. Handle common API and network errors.

## Example

```python
from google import genai
from dotenv import load_dotenv
import os

load_dotenv("llm_api_variables.env")

client = genai.Client(
    api_key=os.getenv("GEMINI_API_KEY")
)

response = client.models.generate_content(
    model="gemini-3.6-flash",
    contents="Explain what an LLM is in one line"
)

print(response.text)
```

## Security

- Keep API keys in local environment files.
- Do not commit `llm_api_variables.env` or `.env` files.
- Rotate your API key immediately if it is accidentally exposed.

## Roadmap

- Multi-turn chat conversations
- Conversation history management
- Tool and function calling
- Structured outputs
- Streaming responses
- Prompt templates
- Evaluation and testing workflows

## License

This project is intended for learning, experimentation, and development of LLM-powered applications.
