#  FastAPI T5 Text Summarizer

A fast and lightweight web application that leverages Natural Language Processing (NLP) to summarize long texts and dialogues. It uses a pre-trained **T5 (Text-to-Text Transfer Transformer)** model from Hugging Face and is built on top of **FastAPI**.

##  Features
- **Local Inference:** Runs the T5 model locally using PyTorch (supports CPU, CUDA, and MPS).
- **FastAPI Backend:** High-performance RESTful API with built-in data validation.
- **Clean UI:** Responsive web interface built with HTML, CSS, and Vanilla JavaScript.
- **Text Preprocessing:** Automatically cleans input text (removes HTML tags, extra spaces, line breaks) before summarizing.

##  Tech Stack
- **Backend:** FastAPI, Uvicorn, Pydantic
- **Machine Learning:** PyTorch, Hugging Face Transformers (`T5ForConditionalGeneration`, `T5Tokenizer`)
- **Frontend:** Jinja2 Templates, HTML, CSS, Vanilla JavaScript

##  Setup & Installation

### 1. Prerequisites
- Python 3.8+ installed.

### 2. Clone the Repository
```bash
git clone https://github.com/your-username/text-summarizer.git
cd text-summarizer
```

### 3. Install Dependencies
Install the required Python packages using `pip`:
```bash
pip install -r requirements.txt
```

### 4. Provide the T5 Model
To keep the repository size small, the heavy ML model weights are ignored from Git via `.gitignore`. Before running the app, you need to provide the T5 model:
1. Create a folder named `saved_summary_model` in the root directory.
2. Download the T5 model (e.g., `t5-small` or `t5-base`) files (`model.safetensors`, `config.json`, `tokenizer.json`, etc.) from Hugging Face and place them inside the `saved_summary_model/` folder.

*(Note: If you don't want to use a local folder, you can modify `app.py` and replace `"./saved_summary_model"` with `"t5-small"` to let the transformers library download it automatically on the first run).*

### 5. Run the Application
Start the FastAPI local server:
```bash
python -m uvicorn app:app --reload
```

### 6. Access the Web App
Open your web browser and go to:
**http://127.0.0.1:8000/**

##  API Reference

### Create a Summary
- **Endpoint:** `/summarize/`
- **Method:** `POST`
- **Content-Type:** `application/json`
    
**Request Payload:**
```json
{
  "dialogue": "Paste your long text or dialogue here that needs to be summarized..."
}
```

**Success Response:**
```json
{
  "summary": "This is the generated summary."
}
```

##  Contributing
Contributions, issues, and feature requests are welcome!

