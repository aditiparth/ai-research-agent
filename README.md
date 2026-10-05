# Autonomous AI Research Agent

An AI-powered research assistant built with **LangChain**, **Anthropic Claude**, and custom tools. The agent searches the web, queries Wikipedia, and outputs structured research data while saving results locally.

## Features

- **Web & Wiki Search:** Uses DuckDuckGo and Wikipedia tools to gather research data.
- **Structured Output:** Enforces strict Pydantic parsing (`ResearchResponse`) for topic, summary, sources, and tools used.
- **File Exporter:** Includes a custom tool to log research results into a local text file.

## Project Structure
├── main.py           # Core agent logic and setup
├── tools.py          # Search, Wikipedia, and file saving tools
├── requirements.txt   # Python dependencies
└── README.md         # Project documentation

## Setup & Installation
1. Clone the RepositoryBashgit clone 
2. Set Up Virtual EnvironmentBash# On macOS/Linux
python3 -m venv venv
source venv/bin/activate

# On Windows
python -m venv venv
venv\Scripts\activate
3. Install DependenciesBashpip install -r requirements.txt
4. Configure Environment VariablesCreate a .env file in the root directory and add your API keys:   Code snippet
ANTHROPIC_API_KEY="your_anthropic_api_key_here"
# OPENAI_API_KEY="your_openai_api_key_here" # Optional if switching to ChatOpenAI

## UsageRun the agent from your terminal:Bashpython main.py
Enter your research query when prompted.   The agent will analyze the request, run required tools (web search, Wikipedia)[cite: 1], and structure the final answer[cite: 1].Output is printed to the console as a structured object and saved locally[cite: 1, 3].

## Technical OverviewLLM: 
Anthropic Claude 3.5 Sonnet (claude-3-5-sonnet-20241022) via langchain-anthropic[cite: 1].
Parser Schema:
class ResearchResponse(BaseModel):
    topic: str
    summary: str
    source: list[str]
    tools_used: list[str]

Tools:
DuckDuckGoSearchRun: Performs real-time web queries.   
WikipediaQueryRun: Retrieves concise Wikipedia topic summaries.   
save_text_to_file: Custom file I/O tool with timestamping.