# Setting up Hermes Agent

Hermes Agent is an AI agent capable of using tools such as the terminal, browser, file system, and code execution to complete tasks autonomously.

Unlike a normal chatbot, Hermes can:

- 📂 Read and modify files
- 💻 Execute terminal commands
- 🌐 Browse the web
- 🤖 Build complete projects
- 🛠️ Debug and fix code
- 📁 Work across multiple files

---

# Step 1: Install Hermes Agent

Open **PowerShell** and run:

```powershell
iex (irm https://hermes-agent.nousresearch.com/install.ps1)
```

After installation, verify it:

```bash
hermes --version
```

Example output:

```
Hermes Agent v0.18.x
Python 3.11
```

---

# Step 2: Create an OpenRouter Account

Visit:

https://openrouter.ai

Sign in using:

- GitHub
- Google

---

# Step 3: Generate an API Key

Navigate to:

Dashboard → Keys

Click:

```
Create API Key
```

Copy the generated key.

Example:

```
sk-or-v1-xxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

> Keep this API key private.

---

# Step 4: Configure Hermes

Run:

```bash
hermes setup
```

Choose:

```
Provider
↓
OpenRouter
```

Paste your API key when prompted.

---

# Step 5: Select a Model

Recommended free model:

```
deepseek/deepseek-v4-flash
```

Other good models:

- qwen/qwen3-8-max *(Paid)*
- anthropic/claude-sonnet-5 *(Paid)*
- openai/gpt-5.5 *(Paid)*

---

# Step 6: Verify Installation

Run:

```bash
hermes doctor
```

You should see:

```
✓ OpenRouter API
✓ Configuration
✓ Browser
✓ Terminal
✓ Memory
```

---

# Step 7: Start Hermes

```bash
hermes
```

You should now see the Hermes interface.

---

# Basic Commands

Start Hermes

```bash
hermes
```

Check configuration

```bash
hermes doctor
```

Change AI model

```bash
hermes model
```

Run setup again

```bash
hermes setup
```

Check version

```bash
hermes --version
```

---

# Example Prompts

Explain REST APIs.

```
Explain what a REST API is.
```

Generate Python code.

```
Create a Python calculator.
```

Create a React component.

```
Build a responsive React landing page using Tailwind CSS.
```

Generate a FastAPI project.

```
Create a FastAPI backend with JWT authentication.
```

---


