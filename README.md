# 🔎 AI Research Agent

A beginner-friendly single-agent AI research application built with:

- **CrewAI** — AI agent framework
- **Groq** — LLM provider
- **OpenAI GPT-OSS 120B** — `openai/gpt-oss-120b`
- **DuckDuckGo** — free web search through `ddgs`
- **Streamlit** — web application
- **GitHub + Streamlit Community Cloud** — deployment

## Project structure

```text
ai-research-agent/
│
├── app.py
├── requirements.txt
├── .gitignore
└── README.md
```

## How it works

```text
User enters research topic
          ↓
      Streamlit
          ↓
     CrewAI Agent
          ↓
 DuckDuckGo Web Search
          ↓
  Groq GPT-OSS 120B
          ↓
   Research Report
          ↓
      Streamlit
```

This project uses **one agent**, **one task**, and **one search tool** to keep the architecture beginner-friendly.

## Deploy directly to Streamlit Community Cloud

You do not need to run this project locally.

### Step 1 — Create a GitHub repository

Create a new repository on GitHub and upload:

```text
app.py
requirements.txt
.gitignore
README.md
```

Do not upload any API key.

### Step 2 — Deploy the repository

Open Streamlit Community Cloud and create a new app.

Select:

- Repository: your GitHub repository
- Branch: `main`
- Main file: `app.py`

Deploy the app.

### Step 3 — Add your Groq API key

After deployment, open your Streamlit app settings.

Go to:

```text
Settings → Secrets
```

Add:

```toml
GROQ_API_KEY = "your_groq_api_key_here"
```

Save the secret and restart/redeploy the app if required.

The application reads the key only from:

```python
st.secrets["GROQ_API_KEY"]
```

The API key is never stored in the GitHub repository.

## Example research topic

Try:

```text
The impact of generative AI on software development
```

The agent will search the web and produce:

- Executive Summary
- Introduction
- Key Findings
- Detailed Analysis
- Conclusion
- Sources

## Important

The agent uses web search results as research input. Search results can contain incomplete or incorrect information.

For important academic, legal, medical, financial, or other high-stakes research, open and verify the original sources.

## Future improvements

After the basic application is working, you can add:

1. Source cards in the Streamlit interface
2. Research-depth options
3. Date filtering
4. PDF/DOCX report export
5. Academic citation styles
6. Source-quality checking
7. Research history
8. Multi-agent verification
