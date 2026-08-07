# Qwen3:4B-Instruct + Hermes Setup Guide

> **Purpose:** Configure Qwen3:4B-Instruct as the default local coding model for Hermes Agent.
>
> **Recommended for:**
> - React & Tailwind CSS
> - FastAPI Backend Development
> - UI/UX Development
> - Debugging
> - Cybersecurity Learning
> - Local AI Coding Assistant

---

# System Specifications

This setup is optimized for:

- CPU: Ryzen 5 7000 Series
- GPU: RTX 3050 6GB
- RAM: 12GB
- Ollama: v0.32.6+
- Hermes Agent: Latest Version

---

# Step 1 - Remove Previous Models (Optional)

If you previously installed the thinking version:

```powershell
ollama rm qwen3-hermes
ollama rm qwen3:4b
```

---

# Step 2 - Pull Qwen3:4B-Instruct

```powershell
ollama pull qwen3:4b-instruct
```

Wait until the download completes.

---

# Step 3 - Verify Installation

```powershell
ollama show qwen3:4b-instruct
```

Expected output should include:

```
Architecture:
qwen3

Context Length:
262144

Capabilities:
✓ completion
✓ tools

Parameters:
num_ctx 65536 (after creating custom model)
```

---

# Step 4 - Create a Working Directory

Create a folder:

```
C:\Users\vaish\ollama-models
```

---

# Step 5 - Create the Modelfile

Inside

```
C:\Users\vaish\ollama-models
```

Create a file named

```
Modelfile
```

Paste the following:

```dockerfile
FROM qwen3:4b-instruct

PARAMETER num_ctx 65536
PARAMETER temperature 0.2
PARAMETER top_p 0.9
PARAMETER top_k 40
PARAMETER repeat_penalty 1.1

SYSTEM """
You are an expert software engineer.

Your specialties include:

- React
- Tailwind CSS
- Next.js
- TypeScript
- FastAPI
- Python
- SQLAlchemy
- Docker
- Linux
- Cybersecurity
- UI/UX

Rules:

• Answer directly.
• Never expose internal reasoning.
• When asked for code, return the finished code first.
• Explain only if requested.
• Produce production-ready code.
• Follow modern best practices.
"""
```

Save the file.

---

# Step 6 - Create the Hermes Model

Open PowerShell.

Navigate to the folder:

```powershell
cd C:\Users\vaish\ollama-models
```

Create the model:

```powershell
ollama create qwen3-hermes -f Modelfile
```

Wait until creation finishes.

---

# Step 7 - Verify Custom Model

```powershell
ollama show qwen3-hermes
```

Expected output:

```
Architecture:
qwen3

Parameters:
4B

Context Length:
262144

Capabilities:
✓ completion
✓ tools

Parameters:
num_ctx 65536
temperature 0.2
top_p 0.9
top_k 40
repeat_penalty 1.1
```

---

# Step 8 - Configure Hermes

Run:

```powershell
hermes model
```

Choose:

```
Custom OpenAI Compatible Endpoint
```

Configure:

| Option | Value |
|---------|-------|
| Display Name | Qwen3 Hermes Local |
| Base URL | http://127.0.0.1:11434/v1 |
| API Compatibility | Chat Completions |
| API Key | ollama |
| Model | qwen3-hermes |
| Context Length | 65536 |

Save the configuration.

---

# Step 9 - Verify Hermes Configuration

The `config.yaml` should contain:

```yaml
model:
  default: qwen3-hermes
  provider: custom
  base_url: http://127.0.0.1:11434/v1
  api_mode: chat_completions
  api_key: ollama
  context_length: 65536
```

---

# Step 10 - Test Ollama

Run:

```powershell
ollama run qwen3-hermes
```

Test prompts:

```
Write a Python Hello World program.
```

```
Generate a modern Tailwind CSS navbar.
```

```
Create a FastAPI CRUD API.
```

Exit using:

```
Ctrl + D
```

or

```
/bye
```

---

# Step 11 - Test Hermes

Start Hermes:

```powershell
hermes
```

Recommended test prompts:

```
Generate a React login page using Tailwind CSS.
```

```
Create a FastAPI authentication system using JWT.
```

```
Debug the following Python code...
```

```
Design a beautiful dashboard UI.
```

---

# Troubleshooting

## Ollama already running

Error:

```
listen tcp 127.0.0.1:11434
```

Solution:

Do **NOT** run

```powershell
ollama serve
```

again.

Verify:

```powershell
tasklist | findstr ollama
```

or

```powershell
ollama ps
```

---

## Check Running Models

```powershell
ollama ps
```

---

## List Installed Models

```powershell
ollama list
```

---

## Remove Model

```powershell
ollama rm qwen3-hermes
```

---

## Recreate Model

```powershell
ollama create qwen3-hermes -f Modelfile
```

---

# Recommended Hermes Settings

Keep these coding-agent integrations disabled unless you explicitly use them:

- claude-code
- codex
- opencode

This allows the local model to answer coding questions directly instead of delegating.

---

# Recommended Workflow

```
You
        │
        ▼
Hermes Agent
        │
        ▼
Qwen3-Hermes
        │
        ├── React
        ├── Tailwind
        ├── FastAPI
        ├── Debugging
        ├── Python
        ├── Cybersecurity
        └── Linux
```

Use cloud models (OpenRouter, NVIDIA NIM, GPT-5, Claude, etc.) only for:

- Large codebases
- Architecture design
- Research
- Complex reasoning
- Multi-agent workflows

---

# Advantages of This Setup

✅ Native 256K context support

✅ Configured runtime context of 64K for Hermes

✅ Lightweight 4B model

✅ Good coding performance

✅ Tool support

✅ Faster than larger local models

✅ Optimized for systems with around 12GB RAM

✅ Suitable for daily software development

---

# Useful Commands

```powershell
ollama list
```

```powershell
ollama ps
```

```powershell
ollama show qwen3-hermes
```

```powershell
ollama run qwen3-hermes
```

```powershell
ollama rm qwen3-hermes
```

```powershell
ollama create qwen3-hermes -f Modelfile
```

```powershell
hermes
```

```powershell
hermes model
```

---

**Version Notes**

- Ollama: 0.32.6+
- Model: qwen3:4b-instruct
- Runtime Context: 65536
- Hermes: Latest compatible release
