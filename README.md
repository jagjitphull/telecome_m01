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
