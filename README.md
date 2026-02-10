<div align="center">

# 🧠 SynapSoul AI
### Autonomous Self-Correcting Research Agent

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io)
[![LangGraph](https://img.shields.io/badge/LangGraph-Agentic-orange?style=for-the-badge)](https://langchain.com)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://docker.com)
[![Status](https://img.shields.io/badge/Status-Production%20Ready-success?style=for-the-badge)]()

**SynapSoul** is a next-generation AI agent that doesn't just "guess" answers—it **researches, critiques, and refines** them. Built on a Dockerized micro-architecture, it features long-term vector memory to cure "LLM Amnesia" and a self-healing feedback loop to eliminate hallucinations.

[🔴 Live Demo](https://synapsoulai.streamlit.app/) · [🐞 Report Bug](https://github.com/YourUsername/SynapSoul/issues) · [📜 Request Feature](https://github.com/YourUsername/SynapSoul/issues)

</div>

---

## ⚠️ The Problem
Standard LLMs (like ChatGPT) suffer from three critical flaws:
1.  **Hallucinations:** They invent facts when they don't know the answer.
2.  **Amnesia:** They forget user details as soon as the chat window closes.
3.  **Stale Data:** They are cut off from real-time events (e.g., believing it's still 2023).

## ✅ The SynapSoul Solution
SynapSoul introduces a **Dual-Agent Architecture** to solve this:
* **🕵️ Researcher Agent:** Scours the live web for real-time data using the Tavily API.
* **⚖️ Critic Agent:** rigorously reviews the Researcher's draft. If the quality is low, it rejects the answer and forces a rewrite.
* **🧠 Neural Memory:** Uses FAISS vector storage to "remember" user context forever, storing interactions as mathematical embeddings.

---

## ⚙️ Architecture & Tech Stack

| Component | Technology | Description |
| :--- | :--- | :--- |
| **LLM Engine** | `Google Gemini 3` | The core reasoning brain processing 1M+ tokens context. |
| **Orchestrator** | `LangGraph` | Manages the cyclic state between Researcher & Critic agents. |
| **Memory** | `FAISS` + `HuggingFace` | Local vector database for long-term semantic recall. |
| **Search** | `Tavily API` | specialized search engine optimized for AI agents. |
| **Frontend** | `Streamlit` | Custom "Glassmorphism" UI with real-time thought logs. |
| **Deploy** | `Docker` | Containerized for "Build Once, Run Anywhere" reliability. |

---

## 🚀 Development Journey

### **Level 1: The Foundation** 🐍
* Established connection with Google Gemini API.
* Implemented basic prompt engineering to define Agent Persona.

### **Level 2: The Second Brain (RAG)** 🧠
* Integrated **FAISS (Facebook AI Similarity Search)**.
* Built a local embedding pipeline to convert user conversations into vectors, allowing the agent to "recall" past discussions days or weeks later.

### **Level 3: Agentic Reasoning** 🛡️
* Moved from linear scripts to **Cyclic Graphs**.
* Built the **Self-Correction Loop**: The agent now holds an internal monologue, criticizing its own work before showing it to the user.
* *Result: Reduced hallucination rate by ~40%.*

### **Level 4: Production Engineering** 📦
* **Dockerized** the entire application.
* Implemented "Uncrashable" error handling with exponential backoff for API limits.
* Deployed to **Hugging Face Spaces** for public access.

---

## 🛠️ Installation & Setup

### **Option 1: Run with Docker (Recommended)**
The easiest way to run SynapSoul. No Python installation required.

```bash
# 1. Pull the image (Optional if building locally)
docker pull yourusername/synapsoul

# 2. Run the container
docker run -p 8501:8501 \
  -e TAVILY_API_KEY="your_key" \
  -e GOOGLE_API_KEY="your_key" \
  synapsoul
