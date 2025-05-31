# Ollama Prompt GitHub Action

This repository hosts a GitHub Actions workflow that allows you to run prompts against an Ollama model using the Ollama REST API.

## Workflow: Ollama Prompt via API (`ollama_prompt.yml`)

This workflow enables you to send a prompt to a specified Ollama model and receive the generated response. It can be triggered manually through the GitHub Actions UI.

### How to Use

1.  Navigate to the "Actions" tab of this repository.
2.  Under "Workflows", select "Ollama Prompt via API".
3.  Click the "Run workflow" button.
4.  Fill in the required and optional input fields:
    *   **`prompt`** (Required): The prompt text you want to send to the Ollama model.
    *   **`model`** (Optional, default: `llama3.2`): The name of the Ollama model to use (e.g., `llama3`, `codellama`).
    *   **`format`** (Optional, default: `json`): The desired format for the API response. Set to `json` for a JSON object.
    *   **`options`** (Optional, default: `{}`): A JSON string to specify advanced Ollama generation options (e.g., `{"temperature": 0.7, "top_p": 0.9}`).
    *   **`stream`** (Optional, default: `false`): Set to `true` to receive a stream of responses. If `false`, the full response is delivered once generation is complete.
    *   **`raw`** (Optional, default: `false`): Set to `true` for raw mode (no template, no system prompt).
    *   **`keep_alive`** (Optional, default: `5m`): Controls how long the model stays loaded in memory after the request. Examples: `5m`, `1h`, `-1` (indefinitely).

5.  Click "Run workflow". The workflow will install Ollama, pull the specified model (using a cache for both for efficiency), send the prompt, and display the LLM's response.

### Features

*   **Manual Trigger**: Easy to run via `workflow_dispatch` with form inputs.
*   **Ollama Installation**: Automatically installs Ollama.
*   **Caching**:
    *   Caches the Ollama binary for faster subsequent runs.
    *   Caches downloaded Ollama models to avoid re-pulling.
*   **Flexible API Interaction**: Supports various parameters of the Ollama `/api/generate` endpoint.

## Credits

This workflow and repository setup were created with the assistance of Jules, an AI software engineering agent developed by Google. You can learn more about similar AI tools and research at [Google AI](https://ai.google/).
