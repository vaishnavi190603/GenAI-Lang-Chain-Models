# GenAI with LangChain 
This repository contains my initial learning and practice while studying **Generative AI and LangChain**.

The learning covers the basic setup of a GenAI project, working with different LLM providers, Hugging Face models, and embedding models.

The concepts are organized into three main areas:

1. **LLM & Chat Models**
2. **Embedding Models**

---

## 1. Project Setup

A Python virtual environment is created so that the libraries required for this project remain isolated from other Python projects.

### Create Virtual Environment

```bash
python -m venv venv
```


### Activate Virtual Environment – Windows

```bash
venv\Scripts\Activate
```

### Install Required Libraries

```bash
pip install -r requirements.txt
```

The `requirements.txt` file contains the Python libraries required for the project.

---

## 2. Testing LangChain Installation

A simple `test.py` file is used to check whether LangChain has been installed successfully.

Example:

```python
import langchain

print("LangChain installed successfully!")
```

The file can be executed using:

```bash
python test.py
```

---

# 3. API Keys and `.env` File

When working with cloud-based LLM providers, API keys are required to authenticate requests.

The API keys are stored in a `.env` file instead of directly writing them inside Python code.

Example:

```env
OPENAI_API_KEY="your-api-key"
ANTHROPIC_API_KEY="your-api-key"
GOOGLE_API_KEY="your-api-key"
HUGGINGFACEHUB_ACCESS_TOKEN="your-token"
```

### Why use `.env`?

It helps keep API credentials separate from the source code.

The `.env` file should **not be uploaded to GitHub**.

It should be added to `.gitignore`:

```text
.env
venv/
__pycache__/
```

---

# 4. Running Python Files

Any Python file can be executed using:

```bash
python filename.py
```
---

# 5. LLM & Chat Models

The first major part of the learning is understanding how applications communicate with different Large Language Models (LLMs).

The main providers explored are:

* OpenAI
* Anthropic Claude
* Google Gemini
* Hugging Face

These models can be accessed through Python and LangChain integrations.

---

## 5.1 OpenAI

OpenAI provides proprietary/closed-source AI models that can be accessed through an API.

### Concepts learned

#### Temperature

Temperature controls the randomness of the model's response.
For example:

```text
Temperature 0
→ Useful for factual and predictable answers

Higher temperature
→ Useful when more creative or varied responses are required
```

### Tokens

Tokens are pieces of text processed by the model.

Simple flow:

```text
User Prompt
     ↓
Input Tokens
     ↓
LLM
     ↓
Output Tokens
     ↓
Response
```

---

## 5.2. Anthropic Claude

Claude is a **closed-source/proprietary model** that is accessed through an API.
Claude is an LLM developed by **Anthropic**.
Claude Sonnet is used as the example model.

---

## 5.3. Google Gemini

The basic concept learned is similar to OpenAI and Claude.

---

## 5.4. Hugging Face

Hugging Face provides access to a large ecosystem of machine-learning and AI models.

Unlike API-only proprietary models, Hugging Face provides many **open-source/open-weight models** that can be used through its ecosystem.

### Repository ID

A **Repo ID** identifies a model on Hugging Face.

It generally looks like:

```text
organization/model-name
```
The Repo ID tells the application which model to use.

---

### Hugging Face Pipeline

The Hugging Face **Pipeline** provides a simple way to use pretrained models for different tasks.

Examples of tasks include:

* Text generation
* Text classification
* Question answering
* Summarization
* Translation
* Sentiment analysis

Basic concept:

```text
Hugging Face Model
       ↓
Pipeline
       ↓
Task
       ↓
Input
       ↓
Output
```

For example:

```text
Repo ID → Model to use

Task → What we want the model to perform
```

---

# 6. Embedding Models

The second major concept is **Embeddings**.

An embedding converts text into a numerical representation called a **vector**.

For example:

```text
"Machine Learning"
        ↓
Embedding Model
        ↓
[0.21, -0.34, 0.72, ...]
```

The vector represents semantic information about the text.

---

## Query Embedding and Document Embedding

Two common concepts are:

### Query Embedding

Converts the user's question/query into a vector.

```text
User Query
    ↓
Embedding Model
    ↓
Query Vector
```

### Document Embedding

Converts a document or piece of text into a vector.

```text
Document
    ↓
Embedding Model
    ↓
Document Vector
```

These vectors can then be compared to find semantically similar information.

### Dimensions

An embedding vector has a fixed number of dimensions.

For example:

```text
[0.21, 0.43, -0.12, 0.88, ...]
```

If an embedding model produces a 768-dimensional vector, the vector contains **768 numerical values**.

The number of dimensions depends on the embedding model.

---

# 7. Cosine Similarity

**Cosine similarity** is used to measure how similar two vectors are.

In a basic semantic-search workflow:

```text
                Query
                  ↓
          Query Embedding
                  ↓
             Query Vector
                  ↓
          Compare Vectors
                  ↑
        Document Embeddings
                  ↑
              Documents
```

If the query vector and document vector are semantically similar, their cosine similarity score will generally be higher.
Ex.
* Semantic Search
* Vector Databases
* RAG
* Document Retrieval
* Question Answering over documents

---


# 8. Overall Learning Flow

The basic flow learned so far is:

```text
Python Environment
       ↓
Create Virtual Environment
       ↓
Install LangChain & Required Libraries
       ↓
Configure API Keys
       ↓
Load LLM / Chat Model
       ↓
Send Prompt
       ↓
Receive Response
```

---

## Learning Source

These notes are based on my learning and practice from the **CampusX Generative AI / LangChain course on YouTube**.

The purpose of this repository is to document my learning step-by-step and build practical understanding by implementing the concepts in Python.
