# Autonomous AI Research Agent

An AI-powered research assistant built with **LangChain** and **Anthropic Claude**. The agent autonomously searches the web and Wikipedia, generates structured research results, and saves them locally.

## Features

- Web search using DuckDuckGo
- Wikipedia research
- Autonomous tool selection with LangChain
- Structured output using Pydantic
- Saves research results to local files

## Tech Stack

**Python · LangChain · Claude 3.5 Sonnet · Pydantic · DuckDuckGo · Wikipedia**

## Project Structure

```text
AI-Agent/
├── main.py
├── tools.py
├── requirements.txt
├── .env
└── README.md
```

## Setup

```bash
git clone https://github.com/aditiparth/ai-research-agent.git
cd AI-Agent

python -m venv venv
venv\Scripts\activate        # Windows

python -m pip install -r requirements.txt
```

Create a `.env` file:

```env
ANTHROPIC_API_KEY="your_api_key_here"
```

Run the agent:

```bash
python main.py
```

Enter a research question when prompted. The agent will select the appropriate tools, gather information, generate a structured response, and save the results locally.

## Example

```text
Input:
What are the applications of AI in healthcare?

Output:
ResearchResponse(
    topic="AI in Healthcare",
    summary="...",
    source=[...],
    tools_used=[...]
)
```

## Future Improvements

- Add more research sources
- Generate PDF/Markdown reports
- Add conversational memory
- Build a web interface
- Add source verification