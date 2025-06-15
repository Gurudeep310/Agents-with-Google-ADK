# 🛠️ Renovation Proposal Generator Agent

This is a study project which defines a Google ADK Agent that generates renovation proposal documents based on user-provided requirements and uploads them as PDFs to Google Cloud Storage.


## 📽️ Demo

▶️ **[Click here to watch the full demo video](media/renovation-proposal-agent.gif)**  

## 🚀 Overview

The agent is designed to assist homeowners and contractors by creating legally structured renovation proposals for remodeling projects. It uses Google Generative AI (`gemini-2.5-pro-preview-03-25`) along with the ReportLab library to generate the proposal content and render it into a PDF.

## ✅ Features

- Accepts renovation requirements from users.
- Generates a sample contract template
- Converts structured content into a professional PDF format.
- Uploads the PDF document to a specified Google Cloud Storage bucket.

## 🧱 Tech Stack
- **Python 3.9+**
- **Gemini Model**
- **Google ADK** (`google-adk==1.3.0`)
- **Google Cloud Storage** for file hosting
- **ReportLab** for PDF generation
- **Dotenv** for managing environment variables

## Usage

### 🔐 Environment Variables

Ensure the following environment variables are set, typically via a `.env` file:

```
GOOGLE_API_KEY=your_google_api_key
STORAGE_BUCKET=your_storage_bucket_name
GOOGLE_CLOUD_PROJECT=your_project_id
GOOGLE_CLOUD_LOCATION=us-central1
GOOGLE_GENAI_USE_VERTEXAI=true
```


### 🧠 How It Works

1. The `root_agent` is initialized with model, instructions, and tool configurations.
2. Upon receiving a user's renovation requirement, the agent formats a contract-style document.
3. The document is passed to the `store_pdf` tool, which:
   - Renders the text using ReportLab.
   - Uploads the result to a GCS bucket.
4. A success message is returned once the upload completes.

## 📦 Dependencies

```
google-adk==1.3.0
pysqlite3-binary==0.5.4
pdfplumber==0.11.7
google-cloud-aiplatform==1.97.0
cloudpickle==3.1.1
pydantic==2.10.6
pytest==8.4.0
overrides==7.7.0
scikit-learn==1.7.0
reportlab==4.4.1
google-cloud-storage==3.1.0
deprecated==1.2.18
```

## 📂 Folder Structure:
```
renovation-agent/
        __init__.py
        agent.py
        requirements.txt
        .env
```

## 🔧 Setup & Installation
Install them using:
1. **Clone the repository:**

```bash
git clone https://github.com/yourusername/renovation-agent.git
cd renovation-agent
python -m venv .venv
source .venv/bin/activate
pip install google-adk
pip install -r requirements.txt
```

📌 Example Question: Hello. Generate Proposal Document for the living room remodel requirement in a proper format that applies to a renovation contract.
