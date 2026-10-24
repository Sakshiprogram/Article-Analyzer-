# Article Analyzer with Hugging Face

An interactive, AI-powered web application that analyzes long text blocks or articles to instantly provide their overall emotional tone and a concise summary. This project utilizes a hybrid AI architecture, combining local machine learning models for speed and cost-efficiency with cloud-powered Large Language Models (LLMs) for high-quality text generation.

---

## 📖 Project Overview

### Goals and Approach
The objective of this project is to build an end-to-end **Article Analyzer** that wraps multiple AI backends inside a professional, easy-to-use user interface. 

*   **Local ML Inference:** Running a local machine learning classification pipeline entirely on-device for rapid sentiment evaluations.
*   **Cloud LLM Integration:** Utilizing cloud-hosted deep learning models to perform complex generative prose creation (summarization) where compact local models reach their accuracy limit.
*   **Unified Interface:** Providing a comprehensive "Full Analysis" workflow that executes both pipelines sequentially in a single action click.

---

## 🛠 Features & Architecture

*   **Local Sentiment Analysis:** Uses a Hugging Face Transformers pipeline (`distilbert-base-uncased-finetuned-sst-2-english`) running entirely on the local machine to classify text as `POSITIVE` or `NEGATIVE` with a precision confidence score.
*   **Cloud-Powered Summarization:** Integrates with OpenRouter's API wrapper to target the powerful `meta-llama/llama-3.3-70b-instruct:free` model, generating highly coherent 2-3 sentence summary blocks.
*   **Full Analysis Mode (Secret Mission):** Orchestrates both local machine learning and cloud pipelines sequentially, returning structured sections side-by-side inside a single cohesive text dashboard.
*   **Polished Web Interface:** Built using a Gradio tabbed layout separating **Summarize**, **Sentiment Analysis**, and **Full Analysis** tasks cleanly.

---

## 📁 Project Structure

```text
article-analyzer/
├── venv/                 # Python virtual environment (ignored by Git)
├── .env                 # Local environment variables containing API keys (ignored by Git)
├── .gitignore           # Specifies intentionally untracked files to keep secrets safe
├── app.py               # Main application source code containing AI pipelines and Gradio UI
├── requirements.txt     # Complete list of Python package dependencies
└── README.md            # Project documentation and setup guide
```

---

## ⚡ Setup and Installation

### Prerequisites
*   **Python 3.10** or higher installed on your machine.
*   A free API key generated from your [OpenRouter Dashboard](https://openrouter.ai).

### 1. Open the Repository Folder
Navigate into your project folder directory:
```powershell
```

### 2. Activate the Virtual Environment
Activate your environment depending on your operating system (ensure execution policies allow scripting on Windows PowerShell):
```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy RemoteSigned
.\venv\Scripts\Activate.ps1
```

### 3. Install Dependencies
Install all documented framework and core tool dependencies:
```powershell
pip install -r requirements.txt
```

### 4. Configure Secrets Securely
Create a `.env` file in the root workspace folder to keep your credentials safe from version control tracking:
```text
OPENROUTER_API_KEY=your-actual-sk-or-key-here
```

---

## 🚀 Running the Application

1. Expose your environment variable inside your active terminal workspace session:
    *   **Windows (PowerShell):** `$env:OPENROUTER_API_KEY="your-actual-sk-or-key-here"`
    *   **Windows (CMD):** `set OPENROUTER_API_KEY=your-actual-sk-or-key-here`
    *   **macOS/Linux:** `export OPENROUTER_API_KEY=your-actual-sk-or-key-here`
2. Launch the server application pipeline:
    ```powershell
    python app.py
    ```
3. Open the running address instance in your local web browser (usually `http://localhost:7860`) to interact with the system interface!

---

## 🧠 Reflections and Key Takeaways

*   **Classification vs. Generation:** Compact local text classification models handle quick sentiment analysis efficiently with zero API costs, whereas complex generative summaries benefit immensely from massive cloud-hosted parameters.
*   **Environment Management:** Isolating packages inside specific directory paths using virtual environments prevents dependency conflicts across library upgrades.
*   **Troubleshooting:** Resolved dependency version mismatches safely on Windows platforms by verifying exact semantic version definitions within tracking configuration matrices.
