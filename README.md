# TermuxAI — Claude Code + Ollama on Android

> Run AI-powered coding tools directly on your Android device. No cloud required.

Live site: [claude-code-termux](https://johndevils.github.io/claude-code-termux/)

---

## What is this?

A cyberpunk-themed landing page for setting up **Claude Code** with **Ollama** models in **Termux** on Android. Full AI development environment in your pocket.

## Quick Start

```bash
# One-liner install
pkg update && pkg upgrade -y && pkg install git nodejs-lts -y && npm i -g @anthropic-ai/claude-code && curl -fsSL https://ollama.com/install.sh | sh
```

## Step-by-Step Setup

### 1. Install Termux Dependencies

```bash
pkg update && pkg upgrade -y
pkg install git nodejs-lts python -y
```

### 2. Install Ollama

```bash
curl -fsSL https://ollama.com/install.sh | sh
ollama serve &
ollama pull codestral
```

### 3. Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
export ANTHROPIC_API_KEY=sk-ant-...
```

### 4. Connect Ollama to Claude Code

```bash
claude config set model ollama:codestral
claude config set ollamaBaseUrl http://localhost:11434
```

### 5. Launch

```bash
mkdir my-project && cd my-project
claude
```

## Supported Models

| Model | Size | Best For |
|-------|------|----------|
| Codestral | 7B | General coding |
| DeepSeek Coder V2 | 33B | Strong reasoning |
| Llama 3.1 | 8B | All-rounder |
| CodeLlama | 34B | Python & JS |
| Qwen2.5-Coder | 7B | Web development |
| Claude (API) | Cloud | Most capable |

## Tech Stack

- Vanilla HTML / CSS / JS
- Tailwind CSS (CDN)
- Mobile-first responsive design
- Zero dependencies beyond Tailwind

## License

MIT — Arsynox / Johndevils