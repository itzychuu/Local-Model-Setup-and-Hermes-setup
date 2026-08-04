# Local-Model-Setup-and-Hermes-setup

Recommended Hardware

Component   Minimum         Recommended

CPU         Modern 4-core   Ryzen 5 / Intel i5 or betterRAM         8 GB            16 GB+GPU         Optional        NVIDIA RTX GPU (6 GB+ VRAM)Storage     15 GB free      30 GB+

What is Ollama?

Ollama is a tool that allows you to run Large Language Models (LLMs)locally on your computer.

Advantages: - Works offline - Privacy-friendly - No subscriptionrequired - Supports many open-source models

Popular models: - Qwen 3 - Llama - Gemma - DeepSeek - Mistral

Installing Ollama

Windows

Download Ollama from: https://ollama.com/download

Install normally.

Verify installation:

ollama --version

Pulling a Model

Example:

ollama pull qwen3:8b

List installed models:

ollama list

Running a Model

ollama run qwen3:8b

Example prompts:

Write a Python program that prints Hello World.

Explain REST APIs.

Exit:

/bye

Managing Models

Show installed models:

ollama list

Remove a model:

ollama rm qwen3:8b

Model information:

ollama show qwen3:8b

What is Hermes Agent?

Hermes Agent is an AI agent capable of:

Reading files

Editing code

Running terminal commands

Browser automation

Project-wide reasoning

Multi-step task execution

Unlike a chatbot, Hermes can use tools to complete tasks.

Installing Hermes (Windows)

Open PowerShell:

iex (irm https://hermes-agent.nousresearch.com/install.ps1)

Verify:

hermes --version

Configure Hermes

Run:

hermes setup

Choose one provider:

Option 1 - Local (Ollama)

Base URL

http://localhost:11434/v1

Model example

qwen3:8b

Note: Hermes requires a model with a reported context window of atleast 64K.

Option 2 - OpenRouter (Recommended)

Create an account.

Generate an API key.

Select OpenRouter during setup.

Choose a supported model.

Example:

deepseek/deepseek-v4-flash

Useful Hermes Commands

hermes

Start the interactive interface.

hermes doctor

Diagnose installation.

hermes setup

Reconfigure providers.

hermes model

Change the active model.

Ollama vs Cloud Models

Local (Ollama)               Cloud (OpenRouter)

Free                         Free & PaidOffline                      Internet requiredPrivate                      Data sent to providerHardware dependent           Powerful hosted modelsLimited by local resources   Large context windows

Understanding Context Window

The context window is the model's working memory.

Examples:

32K

64K

128K

1M

Larger context allows the model to remember: - More code - Longerconversations - More files - Bigger projects

It does not automatically make the model slower; performance dependson both model size and how much of the context is actually used.

Recommended Models

Local

Qwen3 8B

Llama 3.1 8B (if available)

Gemma 3

Cloud

DeepSeek V4 Flash

Qwen 3 Max

Claude Sonnet

Troubleshooting

Ollama not found

ollama --version

Reinstall or restart the terminal.

Hermes reports context window too small

Hermes requires at least 64K reported context.

Use: - A compatible local model, or - OpenRouter / another cloudprovider.

Check Hermes installation

hermes doctor

Suggested Live Demo

Install Ollama.

Pull Qwen3.

Run Qwen3.

Install Hermes.

Configure OpenRouter.

Ask Hermes to create a React landing page.

Review generated code.

Resources

https://ollama.com

https://openrouter.ai

https://github.com/NousResearch/hermes-agent

Happy Building! 🚀
