# 🚀 SkillMap Job Finder Agent

An intelligent, multi-tool AI agent built using **LangChain** and **Google Gemini** that analyzes real-time industry skill demand, evaluates salary trends, and matches users with relevant live job and internship opportunities.

---

## 🛠️ Tech Stack & Architecture
* **Orchestration & Framework:** [LangChain](https://docs.langchain.com/) (`create_agent`, `@tool`)
* **LLM Engine:** [Google Gemini](https://ai.google.dev/) (`gemini-3.5-flash-lite`)
* **Market Trends & Industry Insights:** [Tavily Search API](https://tavily.com/) (`langchain-tavily`)
* **Live Job Data Pipeline:** [JSearch API](https://rapidapi.com/) via RapidAPI & `requests`
* **Environment:** Python / Google Colab

---

## ⚙️ How It Works (Agent Execution Flow)

1. **Natural Language Understanding:** The user provides a free-form career query (e.g., *"What's the demand for software engineers in the industry and show me related job openings in India"*).
2. **Dynamic Parameter Extraction:** The Gemini LLM acts as an intelligent bridge, parsing the query and mapping keywords into structured arguments for each tool based on their exposed schemas.
3. **Step 1 - Demand Analysis (`skill_demand_tool`):** The agent triggers a Tavily search to pull current market growth statistics, tech stack requirements, and location-based salary insights.
4. **Step 2 - Job Matching (`search_jobs`):** The agent extracts targeted parameters (`skill` and `location`) and queries live listings through the JSearch API.
5. **Synthesis & Presentation:** The agent merges market intelligence and verified job listings into a clean, well-spaced summary complete with application links.

---

## 📂 Project Structure

```text
skillmap-job-finder-agent/
│
├── Skill_Map_Agent.ipynb      # Main Google Colab notebook containing the agent logic
├── requirements.txt           # Project dependencies
└── README.md                  # Project documentation
```
---
## 🔑 Setup & Configuration


To run this agent locally or in Google Colab, make sure you configure your environment variables or Google Colab Secrets with the following API keys:

* **GEMINI_API_KEY:** Get your key from Google AI Studio
* **TAVILY_API_KEY:** Get your key from Tavily AI
* **RAPID_API_KEY:** Get your key from RapidAPI (JSearch)

---
## 💡 Example Usage
```text
user_query = "What's the demand for software engineer in the industry and show me related job openings in India"

response = agent.invoke({
    "messages": [
        {"role": "user", "content": user_query}
    ]
})
```
---
## Installation

pip install -qU langchain langchain-google-genai langchain-tavily requests
