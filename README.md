# 🔬 ResearchMind — AI Research Agent

ResearchMind is a **multi-agent AI research system** built with **LangChain, Google Gemini, Tavily, and Streamlit**.

The system uses multiple specialized AI agents to search the web, scrape relevant sources, write a research report, and critically evaluate the final report.

Instead of relying on a single LLM call, ResearchMind uses a **multi-step research pipeline** where each component has a specific responsibility.

## 🚀 Features

- 🔎 Web research using Tavily
- 🤖 AI-powered Search Agent
- 📄 AI-powered Reader Agent
- 🌐 Web page scraping
- ✍️ Automated research report generation
- 🧐 AI-powered report critic
- 📊 Research pipeline visualization
- 📥 Download final report as Markdown
- 🎨 Modern Streamlit interface
- 🔐 Environment variable support
- ⚡ Google Gemini LLM integration

## 🧠 Multi-Agent System

ResearchMind consists of four main components:

### 1. Search Agent 🔎

The Search Agent receives the user's research topic and uses the **Tavily web search tool** to find recent and reliable information.

It collects:

- Source titles
- URLs
- Search snippets
- Relevant web information

### 2. Reader Agent 📄

The Reader Agent receives the search results and selects a relevant URL for deeper investigation.

It uses the `scrape_url` tool to:

- Send an HTTP request to the webpage
- Parse HTML using BeautifulSoup
- Remove scripts, styles, navigation, and footer elements
- Extract clean webpage text
- Return relevant content for further research

### 3. Writer Chain ✍️

The Writer Chain combines the search results and scraped content.

Google Gemini then generates a structured research report containing:

- Introduction
- Key Findings
- Conclusion
- Sources

### 4. Critic Chain 🧐

The Critic Chain reviews the generated research report and provides:

- Score out of 10
- Strengths
- Areas for improvement
- One-line verdict

This creates a **generation → evaluation** workflow.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| LangChain | Agent and LLM orchestration |
| Google Gemini | Large Language Model |
| Tavily | Web search |
| BeautifulSoup | Web scraping |
| Requests | HTTP requests |
| Streamlit | Web interface |
| python-dotenv | Environment variable management |
| Rich | Terminal output and debugging |
| Pydantic | Data validation |

## 📂 Project Structure

```text
ResearchMind/
│
├── app.py
│   └── Streamlit user interface
│
├── agents.py
│   └── Search Agent, Reader Agent,
│       Writer Chain and Critic Chain
│
├── tools.py
│   └── Web search and web scraping tools
│
├── pipeline.py
│   └── Complete research pipeline
│
├── requirements.txt
│   └── Project dependencies
│
├── .env
│   └── API keys and environment variables
│
├── .gitignore
│
└── README.md
⚙️ Installation

Clone the repository:

git clone YOUR_GITHUB_REPOSITORY_URL
cd ResearchMind

Install the dependencies:

pip install -r requirements.txt
🔑 Environment Variables

Create a .env file in the project root:

GOOGLE_API_KEY=your_google_api_key
TAVILY_API_KEY=your_tavily_api_key

The project requires:

Google Gemini API Key — for the LLM
Tavily API Key — for web search

Never commit your .env file to GitHub.

Add the following to .gitignore:

.env
.venv/
__pycache__/
▶️ Run the Application

Start the Streamlit application:

streamlit run app.py

Then open the Streamlit URL in your browser.

🖥️ How to Use
Enter a research topic.
Click Run Research Pipeline.
The Search Agent searches for relevant information.
The Reader Agent scrapes relevant web content.
The Writer Chain generates the research report.
The Critic Chain evaluates the report.
Review the final report and critic feedback.
Download the report as a Markdown file.

Example topics:

LLM agents 2025
CRISPR gene editing
Fusion energy progress
AI automation
Future of robotics
🧩 Core Components
tools.py

Contains the external tools used by the agents:

web_search()
scrape_url()

web_search() uses Tavily to search the web.

scrape_url() uses Requests and BeautifulSoup to extract webpage content.

agents.py

Contains the AI components:

build_search_agent()
build_reader_agent()
writer_chain
critic_chain

The agents use Google Gemini as the underlying LLM.

pipeline.py

Contains the complete research workflow.

It executes:

Search Agent
Reader Agent
Writer Chain
Critic Chain

The intermediate results are stored in a state dictionary.

app.py

Provides the Streamlit interface and connects the UI with the research pipeline.

The interface displays:

Pipeline status
Search results
Scraped content
Final research report
Critic feedback
Download button
📊 Example Output

The generated report contains:

Research Report

Introduction

...

Key Findings

1. ...
2. ...
3. ...

Conclusion

...

Sources

- https://example.com
- https://example.org

The Critic Chain provides feedback such as:

Score: 8/10

Strengths:
- Well structured
- Good coverage of the topic

Areas to Improve:
- More sources could be included
- Some claims need stronger evidence

One line verdict:
A strong research report with room for deeper source validation.
🎯 Learning Objectives

This project demonstrates practical concepts in:

Generative AI
LLM application development
LangChain Agents
Tool Calling
Prompt Engineering
Web Search
Web Scraping
Multi-Agent Systems
AI Research Automation
LLM-based Content Evaluation
Streamlit Application Development
🔮 Future Improvements

Possible improvements include:

Multiple-source research
RAG integration
Vector database integration
Long-term research memory
Automatic report revision based on critic feedback
PDF report generation
Source credibility scoring
Citation verification
More specialized research agents
User authentication
Cloud deployment
👨‍💻 Author

Rohit Roy

GitHub: https://github.com/rohitroy17-gif
