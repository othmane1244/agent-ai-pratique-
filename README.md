# AgentWithUI – Agentic AI with RAG

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-interactive-red.svg)
![RAG](https://img.shields.io/badge/RAG-Retrieval%20Augmented%20Generation-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

**A lightweight Retrieval-Augmented Generation (RAG) agent with Streamlit UI for conversational AI, built for ENSABM training.**

---

## 🎯 Overview

AgentWithUI is an educational project that demonstrates how to build **agentic AI systems** combining:
- **Conversational Interface** – Streamlit-based real-time chat UI
- **RAG Pipeline** – Semantic search with Qdrant vector embeddings
- **LLM Integration** – OpenRouter/OpenAI API for reasoning
- **Tools & Actions** – Web search (SerpAPI), email sending, extensible tool framework
- **Memory Management** – Persistent vector storage for context-aware responses

Perfect for learning AI agent architecture, prompt engineering, and production patterns in minutes.

---

## ✨ Features

- **Interactive Streamlit UI** – Real-time conversation interface
- **Retrieval-Augmented Generation** – Semantic search with Qdrant vector database
- **LLM Integration** – OpenRouter/OpenAI-compatible API client
- **Web Search** – Live information retrieval via SerpAPI
- **Email Tools** – Send emails programmatically
- **Extensible Tools Framework** – Add custom actions and tools easily
- **Environment-based Config** – Simple `.env` setup
- **Production-ready Patterns** – Error handling, logging, async tools

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **UI Framework** | [Streamlit](https://streamlit.io/) |
| **LLM** | [OpenRouter](https://openrouter.ai/) / OpenAI API |
| **Vector DB** | [Qdrant](https://qdrant.tech/) |
| **Embeddings** | OpenAI `text-embedding-3-small` |
| **Search** | [SerpAPI](https://serpapi.com/) |
| **Backend** | Python 3.10+ with LangChain |
| **Runtime** | Local or cloud-deployed |

---

## 📋 Prerequisites

- **Python 3.10+**
- **Windows/Mac/Linux** (commands adapt per OS)
- **Internet connection** (for API calls)
- **Optional:** Qdrant instance (local Docker or cloud)

---

## 🚀 Quick Setup

### 1️⃣ Clone & Navigate

```bash
git clone https://github.com/Ayoub-teaching-repos/Formation_ai_agent-.git
cd AgentWithUI
```

### 2️⃣ Create Virtual Environment

**Windows (PowerShell):**
```powershell
python -m venv venv
venv\Scripts\activate
```

**Mac/Linux (bash/zsh):**
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3️⃣ Install Dependencies

```bash
pip install --upgrade pip
pip install -r requirments.txt
```

### 4️⃣ Configure Environment Variables

Copy the template and add your API keys:

```bash
cp .env.example .env
```

Edit `.env` with your credentials:

```env
# LLM Configuration
OPENROUTER_API_KEY=your_openrouter_api_key_here

# Search Configuration
SERPAPI_KEY=your_serp_api_key_here

# Vector Database
QDRANT_URL=http://localhost:6333

# Email Configuration (optional)
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
EMAIL_SENDER_ADDRESS=your_email@gmail.com
EMAIL_SENDER_PASSWORD=your_gmail_app_password_here
```

### 5️⃣ Run the Application

```bash
streamlit run app.py
```

The app will open at `http://localhost:8501`

---

## 🔑 Getting API Keys (Free Tier Available)

| Service | Steps |
|---------|-------|
| **OpenRouter** | 1. Go to [openrouter.ai](https://openrouter.ai/) <br> 2. Sign up / Log in <br> 3. Copy API key from dashboard |
| **SerpAPI** | 1. Visit [serpapi.com](https://serpapi.com/) <br> 2. Create account <br> 3. Get free credits for search queries |
| **Qdrant** | Option A: Local – `docker run -p 6333:6333 qdrant/qdrant` <br> Option B: Cloud – [cloud.qdrant.io](https://cloud.qdrant.io/) |
| **Gmail SMTP** | 1. Enable 2-factor auth on your Google account <br> 2. Generate [App Password](https://myaccount.google.com/apppasswords) <br> 3. Use as `EMAIL_SENDER_PASSWORD` |

---

## 📁 Project Structure

```
AgentWithUI/
├── app.py                    # Streamlit UI entry point
├── llm.py                    # LLM client & model configuration
├── rag.py                    # RAG pipeline & embeddings
├── memory.py                 # Qdrant vector database connection
├── tools.py                  # Tool definitions (search, email, custom)
├── requirments.txt           # Python dependencies
├── .env.example              # Environment variables template
├── .gitignore                # Git ignore rules
└── README.md                 # This file
```

### File Descriptions

- **app.py** – Streamlit UI with chat interface, model selection, and streaming responses
- **llm.py** – OpenAI-compatible client wrapper for OpenRouter
- **rag.py** – Retrieval-Augmented Generation pipeline with embedding storage/retrieval
- **memory.py** – Qdrant vector database connection and collection management
- **tools.py** – Tool implementations (web search, email, extensible framework)

---

## 🎮 Usage

1. **Start the app** → `streamlit run app.py`
2. **Select a model** → Choose GPT-4 or GPT-3.5-turbo from sidebar
3. **Type your query** → Ask questions or request actions
4. **Agent responds** → LLM processes query, searches web/memory, and responds
5. **Tools execute** → Email, search, or custom tool actions run automatically

### Example Queries

- *"Search for the latest AI news and summarize it for me"*
- *"Send an email to john@example.com saying hello"*
- *"What was mentioned in the last conversation about Python?"*

---

## 🔧 Troubleshooting

| Issue | Solution |
|-------|----------|
| `ModuleNotFoundError: No module named 'streamlit'` | Ensure venv is activated: `venv\Scripts\activate` (Windows) or `source venv/bin/activate` (Mac/Linux) |
| `OPENROUTER_API_KEY not found` | Check `.env` file exists and contains correct key; restart app after editing |
| `Qdrant connection refused` | Start Qdrant: `docker run -p 6333:6333 qdrant/qdrant` or update `QDRANT_URL` to cloud instance |
| `API rate limit exceeded` | Wait or upgrade API tier; check OpenRouter/SerpAPI billing |
| `Email sending failed` | Verify Gmail app password; enable "Less secure apps" if needed |

---

## 📚 Learning Resources

- [Streamlit Docs](https://docs.streamlit.io/)
- [LangChain RAG Guide](https://python.langchain.com/docs/use_cases/question_answering/)
- [Qdrant Documentation](https://qdrant.tech/documentation/)
- [OpenRouter API Docs](https://openrouter.ai/docs)

---

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit changes (`git commit -m "Add your feature"`)
4. Push to branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** – see [LICENSE](LICENSE) file for details.

---

## 💡 Tips & Best Practices

- **Cost Optimization** – Use free tiers initially; monitor API usage
- **Local Development** – Run Qdrant locally with Docker for faster iteration
- **Security** – Never commit `.env` files; use `.env.example` for templates
- **Extensibility** – Add new tools in `tools.py` following the existing pattern
- **Performance** – Cache embeddings and search results to reduce API calls

---

## ❓ FAQ

**Q: Can I use this for production?**  
A: Yes! Follow security best practices (API key rotation, rate limiting, error handling).

**Q: How do I add a new tool?**  
A: Add a function in `tools.py` and register it in the agent's tool registry.

**Q: What if I don't have GPU?**  
A: No GPU needed – embeddings are handled by OpenAI API.

**Q: Can I use a different LLM?**  
A: Yes – OpenRouter supports 100+ models; update `llm.py` for other providers.

---

## 📞 Support

- **Issues** – Open an issue on [GitHub](https://github.com/Ayoub-teaching-repos/Formation_ai_agent-)
- **Discussions** – Use GitHub Discussions for questions
- **Email** – Contact course instructors for training questions

---

**Happy Learning! 🚀**
