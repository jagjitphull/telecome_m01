Here is a complete Markdown file, formatted for GitHub. You can copy the content below, save it as `README.md`, and upload it to a repository.

-----

**File: `README.md`**

````md
# Ollama CLI Guide for Trainees

A step-by-step guide for getting started with Ollama, running models locally, and using the command-line interface (CLI).

## 1. Installation

The installation process differs slightly depending on your operating system.

### On macOS

You have two primary options:

1.  **Recommended (App):**
    * Go to the official website: [ollama.com](https://ollama.com/)
    * Click "Download" and get the `Ollama.app` for macOS.
    * Move the downloaded app to your "Applications" folder.
    * Ollama will run in the background from your menu bar.

2.  **Homebrew (Terminal):**
    * If you use the [Homebrew](https://brew.sh/) package manager:
        ```bash
        brew install ollama
        ```
    * Then, start the Ollama service:
        ```bash
        brew services start ollama
        ```

### On Windows

1.  Go to the official website: [ollama.com](https://ollama.com/)
2.  Click "Download" and get the `OllamaSetup.exe` installer.
3.  Run the installer. Ollama will be set up as a background service, and an icon will appear in your system tray.

### On Linux

1.  Open your terminal.
2.  Run the official installation script using `curl`:
    ```bash
    curl -fsSL [https://ollama.com/install.sh](https://ollama.com/install.sh) | sh
    ```
    This command sets up the `ollama` binary and creates a `systemd` service to run it in the background.

---

## 2. Verifying the Installation

Once installed, open a new terminal window and run the `ollama` command.

```bash
# Check the version to be sure
ollama -v
````

You should see an output like `ollama version is 0.1.0`.

On Linux, you can also check that the background service is running:

```bash
sudo systemctl status ollama
```

-----

## 3\. Core Ollama CLI Commands

All interactions with Ollama happen in your terminal. Here are the most essential commands.

### `ollama pull`: Downloading a Model

Before you can use a model, you need to download (or "pull") it from the Ollama library.

  * **Command:** `ollama pull <model_name>`
  * **Example:** Download `llama3`, Meta's latest model.
    ```bash
    ollama pull llama3
    ```

### `ollama list`: Listing Your Models

To see all the models you have downloaded locally, use this command.

  * **Command:** `ollama list` (or `ollama ls`)
  * **Example:**
    ```bash
    $ ollama list
    NAME            ID              SIZE    MODIFIED
    llama3:latest   a6990ed6be41    4.7GB   5 days ago
    ```

### `ollama run`: Running a Model (Interactive Chat)

This is the most common command. It starts an interactive chat session with a model. **If you don't have the model locally, this command will automatically pull it for you first.**

  * **Command:** `ollama run <model_name>`
  * **Example:**
    ```bash
    ollama run llama3
    ```
    Your terminal will change to an interactive prompt. You can now type your questions:
    ```
    >>> Why is the sky blue?

    The sky appears blue to us because of a phenomenon called Rayleigh scattering...

    >>>
    ```
  * **To exit the chat:** Type `/bye` and press Enter.

### `ollama rm`: Removing a Model

LLM models are large and take up a lot of disk space. You can easily remove them.

  * **Command:** `ollama rm <model_name>`
  * **Example:**
    ```bash
    ollama rm llama3
    ```

### Other Useful Commands

  * `ollama ps`: See which models are currently loaded into memory and running.
  * `ollama stop <model_name>`: Stop a running model and unload it from memory.
  * `ollama help`: Get help and see all available commands.

-----

## 4\. Installing Various Other Models

The true power of Ollama is its access to a massive library of open-source models. You install them all using the same `ollama pull` or `ollama run` command.

A model name is often followed by a **tag** (like `<model>:<tag>`) that specifies its size, quantization, or purpose. If you don't add a tag, `latest` is used.

You can browse all available models at the [Ollama Library](https://ollama.com/library).

### General All-Purpose Chat

  * **Model:** `mistral`
  * **Description:** A high-performance 7B model, known for its speed and quality.
  * **Command:**
    ```bash
    ollama run mistral
    ```

### Coding Assistants

  * **Model:** `codellama`
  * **Description:** A Llama model fine-tuned specifically for code generation and discussion.
  * **Command (Example: 7B Instruct model):**
    ```bash
    ollama run codellama:7b-instruct
    ```

### Small & Fast Models

  * **Model:** `phi3`
  * **Description:** A highly capable 3.8B model from Microsoft that runs very fast, even on less powerful hardware.
  * **Command (Example: 3.8B medium model):**
    ```bash
    ollama run phi3:medium
    ```

### Multimodal (Vision) Models

  * **Model:** `llava`
  * **Description:** This model can understand both text and images.
  * **How to use:**
    1.  Run the model:
        ```bash
        ollama run llava
        ```
    2.  In the prompt, type your question and include the **full path** to an image on your computer.
        ```
        >>> What is in this image? /Users/myname/Desktop/photo.png

        The image shows a golden retriever playing in a park with a red ball...
        ```

<!-- end list -->
