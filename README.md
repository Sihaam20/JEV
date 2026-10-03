# Jev Movie Review Analyzer

A small experiment to understand how **Jev** works.

This project uses Jev to analyze a movie review and make three structured decisions:

* **Noul** → Is the review positive?
* **Choice** → Positive / Negative / Mixed
* **Score** → Sentiment strength

## How It Works

```text
Movie Review
     ↓
    Jev
     ↓
Structured Output
     ↓
Python Logic
```

## Google Colab Setup

### 1. Install requests

```python
!pip install -q requests
```

### 2. Import libraries

```python
import requests
import os
from google.colab import userdata
```

### 3. Add API Key

In Google Colab:

**🔑 Secrets → Add new secret**

Name:

```text
JEV_API_KEY
```

Enable **Notebook access**.

### 4. Load the API Key

```python
os.environ["JEV_API_KEY"] = userdata.get("JEV_API_KEY")

print("Key loaded:", bool(os.environ.get("JEV_API_KEY")))
```

It should show:

```text
Key loaded: True
```

### 5. Run the Movie Review

Enter a movie review and send it to Jev with the three questions.

The result will contain the structured answers.

### 6. Use the Result

```python
if positive_probability > 0.8:
    print("Positive review")
else:
    print("Send to human review")
```

## Example

**Input:**

> The movie was amazing! The acting was excellent and I really enjoyed it.

**Output:**

```text
Positive → 0.99
Category → Positive
Strength → Extremely Positive
```

Possible uses:

* Ticket classification
* Customer support routing
* Document classification
* Workflow automation
* AI agents

## Project Files

```text
jev-movie-review-analyzer/
├── README.md
├── jev.ipynb
└── Requirements.txt
```


