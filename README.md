# 🧠 AI Codebase Mentor

> Understand any GitHub repository instantly with AI-powered analysis, chat, and documentation generation.

[![Python](https://img.shields.io/badge/Python-3.10+-blue)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.35+-red)](https://streamlit.io)
[![LangChain](https://img.shields.io/badge/LangChain-0.2+-green)](https://langchain.com)
[![Groq](https://img.shields.io/badge/Groq-LLaMA3-orange)](https://groq.com)

## Features

- **💬 Chat with Code** — Ask any question about a repository in plain English
- **📋 Repository Summary** — Instant overview of architecture, tech stack, and entry points
- **🐛 Bug Finder** — Detect security vulnerabilities, code smells, and quality issues
- **🏗️ Architecture Diagram** — Generate Mermaid diagrams of system architecture
- **📝 README Generator** — Auto-generate professional README documentation (with download)
- **📁 File Explorer** — Browse files with syntax highlighting and per-file AI explanations
- **⚡ FAISS Vector Search** — Semantic code search with persisted index
- **🔄 Session State** — Cached results, chat history, and selected files across interactions




## Tech Stack

| Layer | Technology |
|---|---|
| UI | Streamlit |
| LLM | Groq (LLaMA-3.3-70B) |
| Orchestration | LangChain |
| Embeddings | HuggingFace sentence-transformers/all-MiniLM-L6-v2 |
| Vector DB | FAISS |
| Git | GitPython |
| Config | python-dotenv |

## Project Structure

```
AI_Codebase_Mentor/
├── app.py                  # Main Streamlit application
├── requirements.txt
├── .env.example
├── repos/                  # Cloned repositories
├── vectorstore/            # Persisted FAISS indices
├── services/
│   ├── clone_repo.py       # GitHub cloning via GitPython
│   ├── loader.py           # Source file loading & stats
│   ├── chunker.py          # RecursiveCharacterTextSplitter
│   ├── embeddings.py       # HuggingFace embeddings (cached)
│   ├── vectorstore.py      # FAISS build/load/persist
│   ├── rag.py              # RAG pipeline & QA chain
│   ├── summary.py          # Repository summary generator
│   ├── bugfinder.py        # Bug & security analysis
│   ├── architecture.py     # Mermaid diagram generator
│   └── readme_generator.py # README.md generator
└── utils/
    └── helper.py           # Shared utilities & constants
```

## Installation

```bash
# 1. Clone this repository
git clone https://github.com/your-username/ai-codebase-mentor
cd ai-codebase-mentor

# 2. Create virtual environment
python -m venv venv
venv\Scripts\activate       # Windows
source venv/bin/activate    # macOS/Linux

# 3. Install dependencies
pip install -r requirements.txt

# 4. Configure environment
cp .env.example .env
# Edit .env and set your GROQ_API_KEY
```

## Configuration

Create a `.env` file in the project root:

```env
GROQ_API_KEY=gsk_your_groq_api_key_here
```

Get a free Groq API key at [console.groq.com](https://console.groq.com).

## Usage

```bash
streamlit run app.py
```

Then open [http://localhost:8501](http://localhost:8501) in your browser.

### Workflow

1. Enter your Groq API key in the sidebar
2. Paste a public GitHub repository URL
3. Click **Clone** to download the repository
4. Click **Build KB** to create the FAISS knowledge base
5. Use any of the six analysis tabs

### Example Questions

```
"Explain the project architecture"
"How does authentication work?"
"What are the main API endpoints?"
"Find potential SQL injection vulnerabilities"
"Explain the login flow"
"What database is used and what's the schema?"
```

## Supported File Types

`.py` `.js` `.ts` `.tsx` `.jsx` `.java` `.cpp` `.c` `.cs` `.go` `.php` `.rb` `.swift` `.kt` `.rs` `.html` `.css` `.sql` `.json` `.yaml` `.yml` `.md` `.sh` `.toml` `.xml` `.vue` `.scss`

## License

MIT License — feel free to use, modify, and distribute.
"# CodeMentorAI" 
