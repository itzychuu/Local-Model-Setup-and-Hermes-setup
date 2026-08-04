# Running Local LLMs with Ollama & Hermes Agent

> Beginner-friendly workshop notes for setting up a local AI coding
> assistant.

------------------------------------------------------------------------

# Prerequisites

## Recommended Hardware

  Component   Minimum         Recommended
  ----------- --------------- ------------------------------
  CPU         Modern 4-core   Ryzen 5 / Intel i5 or better
  RAM         8 GB            16 GB+
  GPU         Optional        NVIDIA RTX GPU (6 GB+ VRAM)
  Storage     15 GB free      30 GB+

------------------------------------------------------------------------

# What is Ollama?

Ollama is a tool that allows you to run Large Language Models (LLMs)
locally on your computer.

Advantages: - Works offline - Privacy-friendly - No subscription
required - Supports many open-source models

Popular models: - Qwen 3 - Llama - Gemma - DeepSeek - Mistral

------------------------------------------------------------------------

# Installing Ollama

## Windows

1.  Download Ollama from: https://ollama.com/download

2.  Install normally.

3.  Verify installation:

``` bash
ollama --version
```

------------------------------------------------------------------------

# Pulling a Model

Example:

``` bash
ollama pull qwen3:8b
```

List installed models:

``` bash
ollama list
```

------------------------------------------------------------------------

# Running a Model

``` bash
ollama run qwen3:8b
```

Example prompts:

    Write a Python program that prints Hello World.

    Explain REST APIs.

Exit:

    /bye

------------------------------------------------------------------------

# Managing Models

Show installed models:

``` bash
ollama list
```

Remove a model:

``` bash
ollama rm qwen3:8b
```

Model information:

``` bash
ollama show qwen3:8b
```

------------------------------------------------------------------------

# What is Hermes Agent?

Hermes Agent is an AI agent capable of:

-   Reading files
-   Editing code
-   Running terminal commands
-   Browser automation
-   Project-wide reasoning
-   Multi-step task execution

Unlike a chatbot, Hermes can use tools to complete tasks.

------------------------------------------------------------------------

# Installing Hermes (Windows)

Open PowerShell:

``` powershell
iex (irm https://hermes-agent.nousresearch.com/install.ps1)
```

Verify:

``` bash
hermes --version
```

------------------------------------------------------------------------

# Configure Hermes

Run:

``` bash
hermes setup
```

Choose one provider:

## Option 1 - Local (Ollama)

Base URL

    http://localhost:11434/v1

Model example

    qwen3:8b

> Note: Hermes requires a model with a reported context window of at
> least 64K.

## Option 2 - OpenRouter (Recommended)

1.  Create an account.
2.  Generate an API key.
3.  Select OpenRouter during setup.
4.  Choose a supported model.

Example:

    deepseek/deepseek-v4-flash

------------------------------------------------------------------------

# Useful Hermes Commands

``` bash
hermes
```

Start the interactive interface.

``` bash
hermes doctor
```

Diagnose installation.

``` bash
hermes setup
```

Reconfigure providers.

``` bash
hermes model
```

Change the active model.

------------------------------------------------------------------------

# Ollama vs Cloud Models

  Local (Ollama)               Cloud (OpenRouter)
  ---------------------------- ------------------------
  Free                         Free & Paid
  Offline                      Internet required
  Private                      Data sent to provider
  Hardware dependent           Powerful hosted models
  Limited by local resources   Large context windows

------------------------------------------------------------------------

# Understanding Context Window

The context window is the model's working memory.

Examples:

-   32K
-   64K
-   128K
-   1M

Larger context allows the model to remember: - More code - Longer
conversations - More files - Bigger projects

It does **not** automatically make the model slower; performance depends
on both model size and how much of the context is actually used.

------------------------------------------------------------------------

# Recommended Models

## Local

-   Qwen3 8B
-   Llama 3.1 8B (if available)
-   Gemma 3

## Cloud

-   DeepSeek V4 Flash
-   Qwen 3 Max
-   Claude Sonnet

------------------------------------------------------------------------

# Troubleshooting

## Ollama not found

``` bash
ollama --version
```

Reinstall or restart the terminal.

## Hermes reports context window too small

Hermes requires at least 64K reported context.

Use: - A compatible local model, or - OpenRouter / another cloud
provider.

## Check Hermes installation

``` bash
hermes doctor
```

------------------------------------------------------------------------

# Suggested Live Demo

1.  Install Ollama.
2.  Pull Qwen3.
3.  Run Qwen3.
4.  Install Hermes.
5.  Configure OpenRouter.
6.  Ask Hermes to create a React landing page.
7.  Review generated code.

------------------------------------------------------------------------

# Resources

-   https://ollama.com
-   https://openrouter.ai
-   https://github.com/NousResearch/hermes-agent

------------------------------------------------------------------------

Happy Building! 🚀
