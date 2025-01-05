# Dria-Node-Run-Full-Guide

## Requirements

### Software

Depending the AI models of your choice, you may have to install software:

- **OpenAI models**: you don't have to install anything, we just need an `OPENAI_API_KEY`!
- **Ollama models**: you have to install Ollama, see [download instructions here](https://ollama.com/download). After installing, confirm you have it with:

  ```sh
  ollama --version
  ```

### Hardware

**To learn about hardware specifications such as required CPU and RAM, please refer to [node specifications](docs/NODE_SPECS.md).**

In general, if you are using Ollama you will need the memory to run large models locally, which depend on the model's size that you are willing to. If you are in a memory-constrained environment, you can opt to use OpenAI models instead.

> [!NOTE]
>
> The compute node is a lightweight process, but you may see increased memory & CPU usage during the initial testing phases, due to various protocol-level operations with the growing network size.

## Setup

To be able to run a node, we need to make a few simple preparations. Follow the steps below one by one.

### 1. Download Files

Download the appropriate ZIP file for your system using the commands below or from [your browser](https://github.com/firstbatchxyz/dkn-compute-launcher/releases). Make sure to replace the URL with the correct version for your operating system and architecture.

#### macOS:

1. Check your architecture:

   ```sh
   uname -m
   ```

   - If the output is `arm64`, download the `arm64` version.
   - If it's `x86_64`, download the `amd64` version.

2. Download the ZIP file:

   ```sh
   # for arm64, use arm64
   curl -L -o dkn-compute-node.zip https://github.com/firstbatchxyz/dkn-compute-launcher/releases/latest/download/dkn-compute-launcher-macOS-arm64.zip
   ```

   ```sh
   # for x86_64, use amd64
   curl -L -o dkn-compute-node.zip https://github.com/firstbatchxyz/dkn-compute-launcher/releases/latest/download/dkn-compute-launcher-macOS-amd64.zip
   ```

3. Unzip the downloaded file:
   ```sh
   unzip dkn-compute-node.zip
   cd dkn-compute-node
   ```

> [!TIP]
>
> Some devices need you to bypass macOS's security warning. If you see "macOS cannot verify that this app is free from malware," when running the node use the following command:
>
> ```sh
> xattr -d com.apple.quarantine dkn-compute-launcher
> ```

#### Linux:

1. Check your architecture:

   ```sh
   uname -m
   ```

   - If it's `aarch64`, download the `arm64` version.
   - If the output is `x86_64`, download the `amd64` version.

2. Download the ZIP file:

   ```sh
   # for aarch64, use arm64
   curl -L -o dkn-compute-node.zip https://github.com/firstbatchxyz/dkn-compute-launcher/releases/latest/download/dkn-compute-launcher-linux-arm64.zip
   ```

   ```sh
   # for x86_64, use amd64
   curl -L -o dkn-compute-node.zip https://github.com/firstbatchxyz/dkn-compute-launcher/releases/latest/download/dkn-compute-launcher-linux-amd64.zip
   ```

3. Unzip the downloaded file:
   ```sh
   unzip dkn-compute-node.zip
   cd dkn-compute-node
   ```

#### Windows:

1. Check your architecture:

   - Open System Information:
     - Press <kbd>⊞ Win + R</kbd> to open the Run dialog.
     - Type `msinfo32` and press <kbd>Enter</kbd>.
   - Look for the line labeled "Processor" or "CPU":
     - If it includes "x64" or refers to Intel or AMD, it is likely x86 (amd64).
     - If it mentions ARM, then it's an ARM processor.

2. Download the ZIP file using a web browser or in PowerShell:

   ```sh
   # for x64, use amd64
   curl -L -o dkn-compute-node.zip https://github.com/firstbatchxyz/dkn-compute-launcher/releases/latest/download/dkn-compute-launcher-linux-amd64.zip
   ```

   ```sh
   # for ARM, use arm64
   curl -L -o dkn-compute-node.zip https://github.com/firstbatchxyz/dkn-compute-launcher/releases/latest/download/dkn-compute-launcher-linux-arm64.zip
   ```

3. Unzip the downloaded file using File Explorer or in PowerShell:
   ```sh
   unzip dkn-compute-node.zip
   cd dkn-compute-node
   ```

### 2. Prepare Environment Variables

With our launcher, setting up the environment variables happen on the fly! The CLI application will ask you to enter the required environment variables if you don't have them.

This way, you won't have to manually do the copying and creating environment variables yourself, and instead let the CLI do it for you. You can move directly on to the [Usage](#usage) section.

### 3. Run a Node and Prepare Your Ethereum Wallet

```sh
# macos or linux
./dkn-compute-launcher
```

```sh
# windows
./dkn-compute-launcher
```

> [!NOTE] Put Your Metamask Wallet Private Key
> 
> Dria makes use of the same Ethereum wallet, that is the recipient of your hard-earned rewards! Place your private key at `DKN_WALLET_SECRET_KEY` without the `0x` prefix. It should look something like:

```sh
DKN_WALLET_SECRET_KEY=ac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80
```

### 4. Setup LLM Provider [Get Your API Key](docs/NODE_SPECS.md)

For the final step, we need to make sure we can serve LLM requests.

#### For OpenAI

If you will be using OpenAI to serve its models, you need to have an API key in the environment.

```sh
OPENAI_API_KEY=<YOUR_KEY>
```

#### For Ollama

First you have to install [Ollama](#requirements), if you haven't already! The compute node is set to download any missing model automatically at the start by default.

#### For Gemini

If you will be using OpenAI to serve its models, you need to have an API key in the environment.

```sh
GEMINI_API_KEY=<YOUR_KEY>
```

> I Am using These
> 
> 5:- OpenAI | o1-mini
> 
> 10: Gemini | gemini-1.5-flash
> 
> 25: OpenRouter | qwq-32b-preview
> 
> 45: Ollama | llama3.2:1b

### Check ur Points

Points - https://steps.leaderboard.dria.co/

### Check Your Ollama Status
You can check the status of your Ollama it's active or not
Make sure it is running. If it shows ‘exited,’ it means your Ollama is not running.
```
sudo systemctl status ollama
```

## 🔶For Next Day Run This Command (Windows)

#1 Open WSL and Put this Command 
```
cd dkn-compute-node
```
#2 Run a Node and Prepare Your Ethereum Wallet
```
./dkn-compute-launcher
```
#3 Setup LLM Provider
