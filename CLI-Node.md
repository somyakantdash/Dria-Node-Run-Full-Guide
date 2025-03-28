# Dria-Node-Run-Full-Guide

## Download Ollama Model

- **Ollama models**: For VPS and WSL(in windows)

  ```
  curl -fsSL https://ollama.com/install.sh | sh
  ```
  
 Check ur Version 
  ```
  ollama --version
  ```
  
## Setup

To be able to run a node, we need to make a few simple preparations. Follow the steps below one by one.

For VPS Only
```
apt install screen -y
```
```
screen -S dria
```

1️⃣ Download Some Files
```
curl -fsSL https://dria.co/launcher | bash
```

3️⃣ Put Code
```
sudo dkn-compute-launcher referrals
```
Use Up & Down Keys to Select "Enter Referral code to be referred" and Enter The Below Refer Code
```
xxxxxxxxxxxx
```
Then Choose & Go Back

4️⃣ Run a Node and Prepare Your Ethereum Wallet
```
sudo dkn-compute-launcher start
```

> Put Your Metamask Wallet Private Key
> Dria makes use of the same Ethereum wallet, that is the recipient of your hard-earned rewards! Place your private key at `DKN_WALLET_SECRET_KEY` without the `0x` prefix. It should look something like:

```
DKN_WALLET_SECRET_KEY=ac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80
```

5️⃣ Setup LLM Provider [Get Your API Key](docs/Top-LLM-Models.md)

For the final step, choose your LLM Models & download it.

#### For Ollama

First you have to install [Ollama](#requirements), if you haven't already! The compute node is set to download any missing model automatically at the start by default.

#### For Gemini

If you will be using OpenAI to serve its models, you need to have an API key in the environment.

```
GEMINI_API_KEY=<YOUR_KEY>
```

> I Am using These (CPU device only)
> 
> Gemini | gemini-1.5-flash | gemini-1.5-pro
> 
> Ollama | llama3.2:1b

> For GPU Device Only
> 
> Ollama | qwen2.5:7b-instruct-fp16
> 
> Ollama | llama3.1:8b-instruct-fp16
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
#2 Setup LLM Provider


# Optional Update Node (If u Facing any Issue)
## 1 Delete Old files
```
cd $HOME
rm -rf .dria
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
