# Knackmore ATS Evaluator

An intelligent resume screening tool that powers [Knackmore.com](https://www.knackmore.com/)'s ATS evaluator. It parses PDF resumes, compares them against target job roles, and returns structured, actionable feedback using AI. Designed for job seekers, recruiters, and developers building smarter hiring workflows.

---

## ✨ Features

* Upload PDF resumes and specify target job roles
* AI-generated ATS score breakdown across 8 categories
* Resume improvement recommendations with examples
* Clean frontend interface built with HTML/CSS/JS
* Flask backend powered by Groq's LLM API
* Markdown-based result formatting
* Support for standalone testing via `test.ipynb`

---

## 🚀 How It Works

1. User uploads a resume and specifies a job title
2. The PDF is parsed and cleaned using PyMuPDF
3. A prompt is crafted and sent to Groq's `llama-3.3-70b-versatile` model
4. The AI responds with ATS scores and feedback in JSON/Markdown
5. Results are displayed beautifully in the frontend

---

## ⚙️ Setup Instructions

### 1. Clone the Repo

```bash
git clone https://github.com/your-username/knackmore-ats-evaluator
cd knackmore-ats-evaluator
```

### 2. Environment Setup

Create and activate a virtual environment:

```bash
conda env create -f environment.yaml
conda activate knackmore
```

OR using pip:

```bash
pip install -r requirements.txt
```

### 3. Environment Variables

Create a `.env` file with:

```env
API_KEY=your-api-key
API_URL=https://api.groq.com/openai/v1/chat/completions
SECRET_KEY=your-flask-secret
```

---

## 🌐 Running the App

```bash
python run.py
```

Go to: `http://localhost:5000`

---

## 🔍 File Overview

| File                      | Purpose                                         |
| ------------------------- | ----------------------------------------------- |
| `run.py`                  | App entry point                                 |
| `config.py`               | Loads API keys and env vars                     |
| `test.ipynb`              | Notebook for standalone score breakdown testing |
| `app/__init__.py`         | Initializes Flask app and routes                |
| `app/routes.py`           | Handles file upload and result routing          |
| `app/resume_evaluator.py` | Handles LLM prompt creation and API calls       |
| `app/utils.py`            | PDF parsing and markdown-to-HTML conversion     |
| `templates/index.html`    | Main UI template                                |
| `static/`                 | Frontend assets (CSS/JS)                        |

---

## 🎓 Powered By

* Flask
* Groq API + LLaMA 3.3 70B
* PyMuPDF (PDF text extraction)
* Markdown + HTML formatting

---

## 🚨 Warning

This tool sends resume data to third-party APIs. Make sure to handle PII responsibly in production environments.

---

## 💼 License

MIT License

---

## 🙏 Acknowledgments

* [Groq](https://groq.com/) for lightning-fast LLM responses
* [PyMuPDF](https://pymupdf.readthedocs.io/) for reliable PDF parsing
* [Markdown](https://daringfireball.net/projects/markdown/) for clean UI formatting
