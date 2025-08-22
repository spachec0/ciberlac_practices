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
> git https://github.com/spachec0/ciberlac_practices.git
> ```

#### 2. Go to challenge directory.
> ```
> cd ciberlac_practices
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



# Challenges

## 1. Prompt Injection

A Prompt Injection Vulnerability occurs when user prompts alter the LLM’s behavior or output in unintended ways. These inputs can affect the model even if they are imperceptible to humans, therefore prompt injections do not need to be human-visible/readable, as long as the content is parsed by the model.

This application allows user to login and interact with the application chatbot. The admin has stored the secret key in his chat history. Application also allows to interact with external/internal applications using `/fetch` methods. 

### Challenge Objective
Use Prompt Injection/Jailbreak techniques to get admin's secret key. 

Application URL: http://127.0.0.1:5001

**Hint:** External URL feature can help


## 2. Data and Model Poisoning

Data poisoning occurs when pre-training, fine-tuning, or embedding data is manipulated to introduce vulnerabilities, backdoors, or biases. This manipulation can compromise model security, performance, or ethical behavior, leading to harmful outputs or impaired capabilities. Common risks include degraded model performance, biased or toxic content, and exploitation of downstream systems.

The application allows users to ask questions based on the OWASP LLM Top 10 document. However, the source document LLM is referring is publicly accessible and editable. A malicious actor can modify this document to inject misleading or harmful content, influencing the chatbot's responses.

### Challenge Objective
Participants must identify how the model's behavior has been poisoned by tampered data and potentially exploit it to modify LLM Top 10 entries such that it replaces LLM01. 

Application URL: http://127.0.0.1:5004

**Hint:** Identify the source


## 3. Improper Output Handling

Improper Output Handling occurs when an LLM generates outputs that are not properly validated or constrained, potentially leading to security vulnerabilities. Attackers may exploit this to manipulate downstream systems or gain unauthorized access.

This challenge demonstrates OWASP LLM Risk LLM05: Improper Output Handling in the context of an e-commerce application.
Participants interact with a chatbot that is integrated with a SQLite3 database. Upon registration, users receive 0 credits. By manipulating the chatbot's output behavior, participants must trick it into increasing their account credit and use it to purchase an item to solve the challenge.

### Challenge Objective

Once register, you login with 0 credits. Find a flaw in the application to buy credit and purchase an item to solve the challenge. 

Application URL: http://127.0.0.1:5005

**Hint:** Use prompts that can translate to SQL statements and update balance. 





## Compatibility 

This project currently supports macOS and Linux systems.

