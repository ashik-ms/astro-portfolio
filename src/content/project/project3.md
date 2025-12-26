---
title: "AI Agent Chatbot with Tool Use and Streaming (LangChain)"
description: "Built a production-ready AI agent using LangChain that dynamically selects tools, streams intermediate reasoning, and delivers verifiable answers using real-time web search and deterministic utilities."
pubDate: "Jun 15 2024"
heroImage: "/agent/hero.png"
tags: ["AI", "LangChain", "LLM", "Agents", "RAG"]
---

## Overview

Large Language Models are powerful, but on their own they can hallucinate, struggle with real-time data, and fail on multi-step reasoning tasks.

In this project, I built a **production-ready AI agent chatbot** using **LangChain** that goes beyond a simple LLM wrapper. The agent is capable of **reasoning, selecting tools dynamically, and streaming both its intermediate steps and final answers** to the user in real time.

The result is a transparent, verifiable, and extensible AI system suitable for real-world applications.

---

## System Architecture


At a high level, the system consists of:
- A **frontend chat interface**
- A **Python FastAPI backend**
- A **LangChain Agent Executor**
- External and internal tools (search, utilities)
- An LLM providing reasoning and response generation

---

## Step-by-Step Flow

![RAG Flow](/agent/image1.png)

1. The **user asks a question** in natural language  
2. The request is sent to a **FastAPI backend**
3. The **LangChain agent analyzes intent**
4. The agent decides whether tools are needed  
5. Tools are executed (search, calculations, etc.)
6. The **LLM generates a grounded answer**
7. Output is **streamed back to the user in real time**

---

## Agent with Tool Calling

The core of the system is an **intelligent multi-tool agent** that:
- Chooses between **no tool**, **retrieval**, or **calculation**
- Chains multiple tools when required
- Prevents hallucinations by grounding responses in tool outputs

### Example
> “Find the current temperature in NYC, multiply it by 5, and report the result in Celsius.”

This requires:
- Web search
- Numeric computation
- Unit conversion  
—all handled autonomously by the agent.

---

## Key Features

### Intelligent Multi-Tool Reasoning
The agent uses **ReAct-style prompting** to reason about which tools to invoke and in what sequence.

### Dynamic Tool Set
- **External tools:** Real-time web search via Serper API  
- **Internal tools:** Deterministic Python utilities (add, multiply, etc.)

### Real-Time Streaming UX
Responses are streamed token-by-token, including:
- Tool selection
- Tool inputs
- Intermediate reasoning
- Final answer

This significantly improves perceived performance and user trust.

### Transparent & Verifiable Output
Final responses include:
- Clearly structured answers
- Citations (when web search is used)
- A list of tools invoked during execution

---

## Technology Stack

- **Language:** Python  
- **Framework:** LangChain (v0.3+)  
- **Web Backend:** FastAPI  
- **LLM Provider:** OpenAI API  
- **Search Tool:** Serper API  
- **Frontend:** Vue-based chat UI  
- **Concepts:** Agents, Tool Calling, Streaming, ReAct prompting  

---

## Why This Project Matters

This project demonstrates my ability to:
- Build **agentic AI systems**, not just LLM wrappers
- Design **transparent, trustworthy AI workflows**
- Implement **real-time streaming architectures**
- Apply modern AI engineering patterns used in production systems

---

## Links

- **GitHub Repository:** https://github.com/ashik-ms/langChainAgent
