# Ciberlac LLM Security Practices 

## This project is intended for AI Security professionals to explore potential security risks in LLMs and learn effective mitigation strategies.

## Overview (No API Key required)

The project is primarily developed using Python and the Ollama framework, with the open source LLM models. The exercises are structured in the form of **CTF (Capture The Flag) challenges**, each with a clear objective, optional hints, and a flag awarded upon successful completion.

## Gettting started

This guide provides instructions for setting up and running the challenges.

### Prerequisites

* Python 3.10 or higher
* pip (Python package installer)
* ollama framework 

### Setup

#### 1. Clone the repository.
> ```
> git clone https://github.com/OWASP/www-project-promptme.git
> ```

#### 2. Go to challenge directory.
> ```
> cd PromptMe
> ```

#### 3. Install the dependencies.
> ```
> pip install -r requirements.txt
> ```

#### 4. Download and Run Ollama

> Download Ollama depending on your OS from https://ollama.com/download
>```
> ollama serve (in the separate terminal)
> ollama pull mistral
> ollama pull llama3
> ollama pull sqlcoder
> ollama pull granite3.1-moe:1b
> ollama pull granite3-guardian

#### 5. Access the application

> ```
> python main.py
> ```
Access the application @ http://127.0.0.1:5000

#### 6. Start the challenge by clicking *start* button on particular category.

## Compatibility 

This project currently supports macOS and Linux systems.

