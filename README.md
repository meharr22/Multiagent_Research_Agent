# ResearchMind

ResearchMind is a multi-agent AI research system that automates web
research, content extraction, report generation, and report evaluation.

The system uses specialized AI agents and LangChain pipelines to
transform a research topic into a structured research report with critic
feedback.

## Live Demo
[Launch ResearchMind](https://multiagentresearchagent.streamlit.app/)

## Overview

ResearchMind follows a four-stage research workflow:

1.  **Search Agent** - Searches the web for recent and relevant
    information.
2.  **Reader Agent** - Selects and scrapes relevant web resources for
    deeper context.
3.  **Writer Chain** - Generates a structured research report from the
    collected information.
4.  **Critic Chain** - Reviews the generated report, assigns a score,
    and provides strengths and areas for improvement.

The application provides an interactive Streamlit interface for running
the complete research pipeline.

## Architecture

``` text
User Research Topic
        |
        v
+-------------------+
|   Search Agent    |
|   Tavily Search   |
+-------------------+
        |
        v
+-------------------+
|   Reader Agent    |
|   Web Scraping    |
+-------------------+
        |
        v
+-------------------+
|   Writer Chain    |
|   Report Creation |
+-------------------+
        |
        v
+-------------------+
|   Critic Chain    |
| Review and Score  |
+-------------------+
        |
        v
Final Research Report
and Critic Feedback
```

## Features

-   Multi-agent AI research workflow
-   Real-time web search using Tavily
-   Web content extraction with BeautifulSoup
-   Agent-based tool calling with LangChain
-   Mistral LLM integration
-   LCEL-based writer and critic chains
-   Structured research report generation
-   Automated report evaluation and scoring
-   Streamlit web interface
-   Pipeline progress visualization
-   Raw search and scraped-content inspection
-   Markdown report download

## Agent Workflow

### Search Agent

The Search Agent uses a Tavily-powered web search tool to gather recent
and reliable information related to the research topic.

### Reader Agent

The Reader Agent uses a scraping tool to extract clean text from a
relevant web resource. Scripts, styles, navigation elements, and footer
content are removed before text extraction.

### Writer Chain

The Writer Chain combines search results and scraped content to generate
a professional research report containing:

-   Introduction
-   Key Findings
-   Conclusion
-   Sources

### Critic Chain

The Critic Chain evaluates the generated report and returns:

-   Score out of 10
-   Strengths
-   Areas to Improve
-   One-line verdict

## Tech Stack

-   Python
-   LangChain
-   LangChain Agents
-   LangChain Expression Language (LCEL)
-   Mistral AI
-   Tavily Search API
-   Streamlit
-   BeautifulSoup
-   Requests
-   python-dotenv

## Project Structure

``` text
MULTIAGENT_SYSTEM/
|
|-- app.py
|-- agents.py
|-- tools.py
|-- pipeline.py
|-- requirements.txt
|-- .gitignore
`-- README.md
```

### File Description

  -----------------------------------------------------------------------
  File                                Purpose
  ----------------------------------- -----------------------------------
  `app.py`                            Streamlit user interface and
                                      interactive pipeline execution

  `agents.py`                         Search Agent, Reader Agent, Writer
                                      Chain, and Critic Chain

  `tools.py`                          Tavily web search and URL scraping
                                      tools

  `pipeline.py`                       Command-line orchestration of the
                                      complete research pipeline

  `requirements.txt`                  Python project dependencies

  -----------------------------------------------------------------------

## Installation

### 1. Clone the repository

``` bash
git clone https://github.com/YOUR_USERNAME/ResearchMind.git
cd ResearchMind
```

### 2. Create a virtual environment

``` bash
python -m venv venv
```

Activate it on Windows:

``` bash
venv\Scripts\activate
```

Activate it on macOS or Linux:

``` bash
source venv/bin/activate
```

### 3. Install dependencies

``` bash
pip install -r requirements.txt
```


### 4. Configure environment variables

Create a `.env` file in the project root:

``` env
MISTRAL_API_KEY=your_mistral_api_key
TAVILY_API_KEY=your_tavily_api_key
```

Never commit the `.env` file or expose API keys publicly.

## Run the Application

Start the Streamlit application:

``` bash
python -m streamlit run app.py
```

The application will open in your browser. Enter a research topic and
run the research pipeline.

## Run the Command-Line Pipeline

You can also execute the research workflow from the terminal:

``` bash
python pipeline.py
```

Enter a research topic when prompted.

## Example Workflow

``` text
Research Topic:
LLM agents in 2025

Search Agent
    |
    v
Collects recent web results

Reader Agent
    |
    v
Extracts detailed content

Writer Chain
    |
    v
Generates structured report

Critic Chain
    |
    v
Scores and reviews report
```

## Key Concepts Demonstrated

This project demonstrates:

-   Multi-agent AI systems
-   Tool calling
-   Agent specialization
-   Web search integration
-   Web scraping
-   LLM orchestration
-   LangChain agents
-   LCEL pipelines
-   Prompt engineering
-   State-based pipeline execution
-   AI-generated content evaluation



## Author

**Mehar Arora**


