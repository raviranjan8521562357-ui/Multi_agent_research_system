# ResearchMind - Multi-Agent AI Research System

ResearchMind is a Streamlit application that uses a multi-agent LangChain workflow to research a user-provided topic, scrape deeper web content, write a structured report, and critique the final output.

## Features

- Search agent for recent web information using Tavily
- Reader agent for scraping relevant web pages
- Writer chain for generating a structured research report
- Critic chain for scoring and reviewing the report
- Streamlit UI with pipeline status and report download
- Optional command-line pipeline through `pipeline.py`

## Project Structure

```text
Multi_Agent_System/
├── app.py              # Streamlit web interface
├── agents.py           # LangChain agents and writer/critic chains
├── tools.py            # Tavily search and URL scraping tools
├── pipeline.py         # Command-line research pipeline
├── requirements.txt    # Python dependencies
├── .env                # API keys and environment variables
└── README.md
```

## Requirements

- Python 3.11 recommended
- Tavily API key
- Mistral API key

## Setup

1. Open the project folder:

```powershell
cd D:\AI_Projects\Multi_Agent_System
```

2. Install dependencies:

```powershell
python -m pip install -r requirements.txt
```

If Streamlit is using Python 3.11 directly, install with:

```powershell
C:\Users\acer\AppData\Local\Programs\Python\Python311\python.exe -m pip install -r requirements.txt
```

3. Create or update `.env`:

```env
TAVILY_API_KEY="your_tavily_api_key"
MISTRAL_API_KEY="your_mistral_api_key"
```

## Run the Streamlit App

Use Streamlit to start the web app:

```powershell
streamlit run app.py
```

Then open:

```text
http://localhost:8501
```

If the `streamlit` command uses Python 3.11 on your machine, you can run it explicitly:

```powershell
C:\Users\acer\AppData\Local\Programs\Python\Python311\Scripts\streamlit.exe run app.py
```

## Run the CLI Pipeline

You can also run the research pipeline from the terminal:

```powershell
python pipeline.py
```

Enter a research topic when prompted.

## Workflow

1. The Search Agent searches the web for recent and reliable information.
2. The Reader Agent selects a relevant URL and scrapes deeper content.
3. The Writer Chain combines the gathered research into a report.
4. The Critic Chain reviews the report and provides a score, strengths, improvements, and verdict.

## Troubleshooting

### `ModuleNotFoundError: No module named 'tavily'`

Install `tavily-python` in the same Python environment used by Streamlit:

```powershell
python -m pip install tavily-python
```

If Streamlit is using Python 3.11:

```powershell
C:\Users\acer\AppData\Local\Programs\Python\Python311\python.exe -m pip install tavily-python
```

Then restart Streamlit and refresh the browser.

### Streamlit warning when running `python app.py`

`app.py` is a Streamlit app, so run it with:

```powershell
streamlit run app.py
```

### API key errors

Check that `.env` contains valid values for:

```env
TAVILY_API_KEY
MISTRAL_API_KEY
```

## Notes

- Do not commit real API keys to a public repository.
- The final report can be downloaded as a Markdown file from the Streamlit UI.
- Web search quality depends on Tavily results and the availability of scraped web pages.
