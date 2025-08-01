## 🧠 LangGraph + LangChain: Tools, Memory, and Multi-Step Reasoning

This project demonstrates how to build a stateful multi-step agent workflow using LangGraph, LangChain, and external APIs such as Google Serper and OpenAI. It includes tool use, decision logic, memory handling, and agent orchestration in a graph-based system.

🚀 Project Overview
This notebook builds an AI assistant that:

1. Takes user queries

2. Searches Google using Serper API

3. Makes decisions using tools

4. Stores and references memory

5. Uses LangGraph to define custom flows and logic

6. It also includes a Gradio interface for interactive testing.

📁 Project Structure
W4_1_2_Langgraph_tools_memory.ipynb: Main implementation notebook

Uses LangChain, LangGraph, LangChain_OpenAI, and LangChain_Community

Configures tools and memory for agent

Defines a graph-based execution plan

🛠️ Setup Instructions
1. Install Required Libraries
bash
Copy
Edit
pip install -U langgraph langchain_openai langchain_community gradio
2. Set Environment Variables
python
Copy
Edit
import os
os.environ["LANGCHAIN_TRACING_V2"] = "true"
os.environ["LANGCHAIN_API_KEY"] = "your_langsmith_api_key"
os.environ["SERPER_API_KEY"] = "your_google_serper_api_key"
os.environ["OPENAI_API_KEY"] = "your_openai_api_key"
🧩 Key Components
🧠 LangGraph
LangGraph is used to build a custom agent workflow using a graph. Nodes represent tasks, and edges control how information flows between tasks.

🔍 Google Serper Tool
Integrated with LangChain to fetch real-time Google search results.

🧰 Tools
Custom tools are defined using ToolNode, and the system conditionally decides which tool to use with tools_condition.

🧾 Memory Handling
Includes basic message memory and adds messages between nodes to simulate persistent state.

🧪 Testing
A simple Gradio interface is created to allow users to test the agent by inputting queries.

⚙️ Example Flow
User inputs a query via Gradio.

LangGraph kicks off the process at the START node.

Based on the question, a tool is conditionally selected.

The tool fetches results using the Serper API.

The response is passed along the graph, updated with memory.

Final output is displayed to the user.

📷 Screenshot / Diagram
Not included here, but you can use the IPython.display.Image block from the notebook to visualize graph flow.

📌 Notes
Make sure to set your environment variables before running the notebook.

Replace placeholder API keys (LangsmithAPI, Serper, etc.) with real ones.

To deploy this as an app, wrap the Gradio interface into app.py and host it on Hugging Face or a web server.
