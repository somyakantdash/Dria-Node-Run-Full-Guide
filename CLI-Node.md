# Dria-Node-Run-Full-Guide

### Offical Docs Guide - https://firstbatch.notion.site/How-to-Run-a-Dria-Node-4529a889692940ca8514427cc5ea4c70

## Download Ollama Model

- **Ollama models**: For VPS and WSL(in windows)
  ```
  curl -fsSL https://ollama.com/install.sh | sh
  ```
  
 Check ur Version 
  ```
  ollama --version
  ```

**Windows or Command Prompt (CMD)**
Go: https://ollama.com/download

1️⃣ Dependencies for WINDOWS & LINUX & VPS
```
sudo apt update
sudo apt upgrade -y
```

For VPS Only
```
apt install screen -y
```
```
screen -S dria
```

2️⃣ Download Some Files in WSL or Ubuntu
```
curl -fsSL https://dria.co/launcher | bash
```
**Windows or Command Prompt (CMD)**
```
powershell -c "irm https://dria.co/launcher.ps1 | iex"
```

3️⃣ Run a Node and Prepare Your Ethereum Wallet
```
sudo dkn-compute-launcher start
```
**Windows or Command Prompt (CMD)**
```
dkn-compute-launcher.exe start
```

> Put Your Metamask Wallet Private Key
> Dria makes use of the same Ethereum wallet, that is the recipient of your hard-earned rewards! Place your private key at `DKN_WALLET_SECRET_KEY` without the `0x` prefix. It should look something like:

```
DKN_WALLET_SECRET_KEY=ac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80
```

5️⃣ Setup LLM Provider [Get Your API Key](docs/Top-LLM-Models.md)

### Models Menu

When you select <kbd>Model</kbd> option in the Settings menu, you will be greeted with another menu:
where you can navigate with arrow keys <kbd>↑</kbd> <kbd>↓</kbd> and select an option with enter <kbd>ENTER</kbd>

```py
? Choose model settings:
> Edit model selection
  List chosen models
  Remove local models
  Measure local models
```

#### Selecting Models

Click on `Edit model selection` to select models for your node.

```sh
? Select a model provider:
> ollama
  openai
  gemini
  openrouter
  VLLM
  ← Go Back
```

Here, you can select a provider to choose models served by them, where you will be greeted with the following menu:

```sh
> Select a model provider: openai
? Choose your models with SPACE, then press ENTER:
  [ ] gpt-4-turbo
  [x] gpt-4o
> [ ] gpt-4o-mini
  [ ] o1-mini
  [ ] o1-preview
  [ ] o1
  [ ] o3-mini
# ...
```

#### For Ollama

First you have to install [Ollama](https://ollama.com/download), if you haven't already! The compute node is set to download any missing model automatically at the start by default.

#### For Gemini

```
GEMINI_API_KEY=<YOUR_KEY>
```
Free on OpenRouter but also offers a paid plan. Provides up to 1,500 free requests daily with no cost and doesn’t require VPS resources. Powered by Google’s API. Get your Google API here. https://aistudio.google.com/app/apikey

> I Am using These (CPU & GPU Both Deevice)
> 
> Gemini | gemini-1.5-flash | gemini-1.5-pro
> 
> Ollama | llama3.2:1b
>
> Ollama | deepseek-r1:1.5b

> For GPU Device Only
> 
> Ollama | qwen2.5:7b-instruct-fp16
> 
> Ollama | llama3.1:8b-instruct-fp16
>
> Ollama | deepseek-r1:1.5b
> 
> Ollama | deepseek-r1:1.5b
> 
> Open AI | gpt-4o (paid)
> 
> Meta | meta-llama/llama-3.1-8b-instruct (paid)

For VPS Only
```
PRESS CTRL+A+D (to run ur node continuously)
```
For VPS Only (to check ur node again)
```
screen -r dria
```

### Check ur Points

Points - https://dria.co/edge-ai

### Check Your Ollama Status
You can check the status of your Ollama it's active or not
Make sure it is running. If it shows ‘exited,’ it means your Ollama is not running.
```
sudo systemctl status ollama
```

## 🔶For Next Day Run This Command (Windows)

#1 Open WSL and Put this Command 
```
sudo dkn-compute-launcher start
```
**Windows or Command Prompt (CMD)**
```
dkn-compute-launcher.exe start
```


# Optional Update Node (If u Facing any Issue)
## 1 Delete Old files in WSL
```
cd $HOME
rm -rf .dria
```
**Windows or Command Prompt (CMD)**
```
rd /s /q "%USERPROFILE%\.dria"
```
### Extra
```
cd $HOME
rm -rf dkn-compute-node.zip
rm -rf dkn-compute-node
```

## 2 Stop Nodes and Stop Ollama Node
```
pgrep ollama
```
### Example: if 74877, then use
kill 74877

## THEN Stop Ollama
```
sudo systemctl stop ollama
sudo systemctl disable ollama
```

**Stop Dria (Terminate screen for VPS)**
```console
screen -XS dria quit
```

## 3 Update and Rerun node
Start from Step [Install Dria](https://github.com/somyakantdash/Dria-Node-Run-Full-Guide/)
