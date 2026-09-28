# Ollama Terminal Coding Assistant

A lightweight terminal-based AI coding assistant that enables you to interact with an Ollama model directly from your shell. It provides commands to list files, read/write files, and execute shell commands, all driven by natural language.

## Features

- List directory contents
- Read and write files
- Execute shell commands (with confirmation)
- Natural language interaction powered by Ollama's nemotron-3-nano:30b-cloud model
- Easy to integrate into scripts

## Prerequisites

- Python 3.8+
- Ollama installed and running
- Access to the nemotron-3-nano:30b-cloud model (run `ollama pull nemotron-3-nano:30b-cloud`)
- An API key for Ollama (or OpenAI) with model access
- Optional: `uv` package manager (recommended for fast dependency handling)

## Installation

1. Clone the repository
2. (Optional) Create a virtual environment with `uv`  
   ```bash
   uv venv .venv
   ```
3. Install dependencies using `uv`:
   ```bash
   uv pip install openai python-dotenv
   ```
   *You may also use `pip install` if you prefer the standard workflow.*
4. Create a `.env` file with `OLLAMA_API_KEY=your-key`
5. Pull the model:
   ```bash
   ollama pull nemotron-3-nano:30b-cloud
   ```

## Quick Start

Run the script with `uv`:

- **Windows (PowerShell)**
  ```powershell
  uv run .\__init__.py
  ```
- **macOS / Linux**
  ```bash
  uv run __init__.py
  ```

Then interact with the assistant using commands such as:

- `list_files`
- `read_file <path>`
- `write_file <path> <content>`
- `run_command <command>` (you will be asked for confirmation)

## Configuration

- `OLLAMA_API_KEY` – Your Ollama API key
- `OPENAI_API_KEY` – If using an OpenAI-compatible model
- Change the `MODEL` constant in the source to use a different model

## Example Usage

**User:** `list_files`  
**Assistant:** `.  __init__.py/  .env/`

**User:** `read_file __init__.py`  
**Assistant:** *(file contents displayed)*

**User:** `write_file example.txt Hello, world!`  
**Assistant:** `Saved example.txt (16 characters)`

**User:** `run_command echo Hello!`  
```
  Run 'echo Hello!'? [y/N] y
  Hello!
```

## Contributing

Fork the repository, create a feature branch, submit a pull request.

## License

MIT License