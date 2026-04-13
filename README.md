Install Cloud Code In Termux Using Olama

A lightweight setup to turn your Android device into a local AI-powered coding environment using Termux.

🚀 Overview
You will build:
Termux → Linux environment on Android
Ollama → Local AI model server
Claude Code → AI coding assistant

⚙️ Requirements
Android phone (4GB+ RAM recommended)
Stable internet
Termux (from F-Droid)

🚀 Architecture Overview
Termux (Host Layer) → Runs Ollama (LLM server)
Claude Code (CLI) → Connects to Ollama for AI coding

🛠️ INSTALLATION
🧠 Part 1 — Install Ollama (Termux)
1. Update and install dependencies
pkg update && pkg upgrade -y
pkg install git nodejs-lts python -y
pkg install ollama


2. Start Ollama server
ollama serve


3. Download Kimi model
⚠️ Requires strong internet (cloud model).
ollama pull kimi-k2.5:cloud


🤖 Part 2 — Install Claude Code (Termux)
1. Install Claude Code
npm install -g @anthropic-ai/claude-code


2. Configure connection to Ollama
echo -e '\n# Claude Code with Ollama Config\nexport ANTHROPIC_BASE_URL="http://localhost:11434"\nexport ANTHROPIC_AUTH_TOKEN="ollama"' >> ~/.bashrc && source ~/.bashrc


3. Run Claude Code with Kimi
claude --model kimi-k2.5:cloud


🔗 System Workflow
Termux
 ├── Ollama (LLM Server :11434)
 └── Claude Code (AI CLI)

Claude Code → sends requests to Ollama
Entire system runs locally on your phone

⚡ Usage Workflow
Start Ollama:
ollama serve

Run Claude Code:
claude --model kimi-k2.5:cloud


⚠️ Important Notes
Keep Ollama running before using Claude Code
:cloud models require internet (not fully offline)
Performance depends on network + device
Close background apps for stability

🛠️ Troubleshooting
Claude cannot connect to Ollama
Ensure ollama serve is running
Check port 11434

