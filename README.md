# AgentWithUI

Minimal README for the AgentWithUI project (Streamlit + RAG agent).

## Project

This project is a small Retrieval-Augmented Generation (RAG) agent with a Streamlit UI.

## Prerequisites

- Python 3.10 or newer
- Windows (commands below use Windows paths)

## Setup (Windows)

1. Create and activate a virtual environment

```powershell
python -m venv venv
venv\Scripts\activate
```

2. Install Python dependencies

```powershell
pip install --upgrade pip
pip install -r requirments.txt
```

Note: the dependency file in this repository is named `requirments.txt` (typo preserved).

3. Create a `.env` file at the project root containing required secrets and endpoints. Example:

```
OPENROUTER_API_KEY=your_openrouter_api_key
SERPAPI_KEY=your_serp_api_key
QDRANT_URL=http://localhost:6333
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
EMAIL_SENDER_ADDRESS=you@example.com
EMAIL_SENDER_PASSWORD=your_email_password
```

The code references these environment variables: `OPENROUTER_API_KEY`, `SERPAPI_KEY`, `QDRANT_URL`, `SMTP_SERVER`, `SMTP_PORT`, `EMAIL_SENDER_ADDRESS`, and `EMAIL_SENDER_PASSWORD`.

### API Links

- **OpenRouter API**: https://openrouter.ai/ - Get your API key from the dashboard
- **SerpAPI**: https://serpapi.com/ - Get your API key from account settings
- **Qdrant**: https://qdrant.tech/ - Download or use cloud version at https://cloud.qdrant.io/
- **Gmail SMTP**: Use your Gmail account with [App Passwords](https://myaccount.google.com/apppasswords) for `EMAIL_SENDER_PASSWORD`

## Run

Activate the virtual environment (if not already) then run Streamlit:

```powershell
venv\Scripts\activate
streamlit run app.py
```

Or from project root (PowerShell):

```powershell
streamlit run .\app.py
```

## Troubleshooting

- If `streamlit` is not found, ensure the virtual environment is activated and `streamlit` is installed (`pip install streamlit`).
- If API calls fail, verify the keys in the `.env` file and that the variables are loaded.
- If Qdrant is used and not reachable, either run a Qdrant instance locally or update `QDRANT_URL` to a reachable endpoint.

## Notes

- The project uses an OpenAI-compatible client via the OpenRouter key variable (`OPENROUTER_API_KEY`).
- If you add or change dependencies, update `requirments.txt` and reinstall with `pip install -r requirments.txt`.

---


