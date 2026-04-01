# Research Agent (CrewAI + Streamlit + Docker)

## Overview

This project is a Python-based research agent built using **CrewAI**, **Streamlit**, and **Docker**. The application allows users to run an intelligent research workflow powered by LLM agents through a simple web interface.

The agent collects information from external sources, processes it using structured reasoning, and presents results interactively inside a Streamlit dashboard.

---

## Features

* CrewAI-based multi-agent research workflow
* LLM-powered reasoning and summarization
* Streamlit web interface for interaction
* External search tool integration (SerperDevTool supported)
* Environment-variable-based configuration
* Fully containerized using Docker
* Easy deployment and reproducibility

---

## Project Structure

```
Research_Agent/
│
├── tasks/
│   └── analysis_task.py
│   └── research_agent.py
│   └── writing_task.py
│
├── agents/
│   └── content_writer.py
│   └── data_analyst.py
│   └── research_specialist.py
│
├── app.py
├── crew.py
├── requirements.txt
├── dockerfile
├── .env
├── .dockerignore
└── README.md
```

---

## Tech Stack

* Python
* CrewAI
* Streamlit
* Docker

---

## Installation (Local Setup)

### 1. Clone the repository

```
git clone https://github.com/heyiamsouvik/Reasearch_agent_CrewAI.git
cd Research_Agent
```

### 2. Create virtual environment

Windows:

```
python -m venv venv
venv\Scripts\activate
```

Linux / Mac:

```
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```
pip install -r requirements.txt
```

---

## Environment Variables

Create a `.env` file in the root directory:

```
GROQ_API_KEY=your_key_here
SERPER_API_KEY=your_key_here
RESEARCH_AGENT_LLM=groq/llama-3.3-70b-versatile
ANALYST_AGENT_LLM=groq/llama-3.3-70b-versatile
WRITER_AGENT_LLM=groq/llama-3.3-70b-versatile
RESEARCH_AGENT_TEMPERATURE=0.1
ANALYST_AGENT_TEMPERATURE=0.2
WRITER_AGENT_TEMPERATURE=0.3
```

Modify values based on your provider configuration.

---

## Run Application (Without Docker)

Start Streamlit server:

```
streamlit run app.py
```

Open browser:

```
http://localhost:8501
```

---

## Run Application Using Docker

### 1. pull Docker image

```
docker pull heyiamsouvik/researchagent:1.0
```

### 2. Run container

Create a `.env` file in the root directory

```
docker run -p 8501:8501 --env-file .env researchagent:1.0
```

Open:

```
http://localhost:8501
```

---



## How the Agent Works

1. User submits research topic via Streamlit UI
2. CrewAI agent receives structured task
3. Search tool gathers external context
4. LLM processes findings
5. Output returned to Streamlit interface

---

## Example Use Cases

* Academic topic research
* Technical documentation exploration
* Market research summaries
* Concept explanations
* Knowledge aggregation workflows

---

