# 🚀 Operator Agent – AI Browser Sidekick

Build your own version of an Operator-style AI agent.

This project implements a **stateful multi-agent AI Sidekick** using **LangGraph**, capable of autonomous reasoning, tool execution, and iterative task refinement based on user-defined success criteria.

---

## 📌 Overview

The Operator Sidekick is an intelligent assistant that:

- Executes multi-step tasks autonomously  
- Uses external tools when necessary  
- Evaluates its own responses  
- Retries automatically if success criteria are not met  
- Maintains memory across interactions  

Unlike basic chatbots, this system uses a **graph-based orchestration engine** to manage reasoning loops and structured decision-making.

---

## 🏗️ Architecture

The system is built using a **LangGraph state machine**:

```
START → Worker → (Tools?) → Evaluator → Retry or END
```

### 🔹 Core Components

### 1️⃣ Worker Agent
- Uses LLaMA 3.1 (via Groq)
- Performs reasoning
- Calls tools when required
- Attempts to satisfy success criteria

### 2️⃣ Tool Node
- File management tools
- Wikipedia search tool
- Extensible for browser automation (Playwright-ready)
- Designed for easy tool expansion

### 3️⃣ Evaluator Agent
- Validates final output
- Checks against success criteria
- Provides structured feedback
- Decides whether to retry or terminate

### 4️⃣ Memory System
- Uses `MemorySaver` checkpointing
- Thread-based state management
- Enables persistent multi-step workflows

---

## 🛠️ Tech Stack

- **Python**
- **LangGraph**
- **LangChain**
- **Groq (LLaMA 3.1)**
- **Gradio**
- **Pydantic (Structured Output Validation)**
- **Playwright (Optional Browser Automation)**

---

## ⚙️ Key Features

✅ Stateful multi-agent architecture  
✅ Worker–Evaluator feedback loop  
✅ Tool-calling LLM integration  
✅ Structured output validation  
✅ Conditional graph routing  
✅ Async execution support  
✅ Interactive web UI with Gradio  
✅ Memory checkpointing  

---

## 📂 Project Structure

```
.
├── app.py               # Gradio UI entry point
├── sidekick.py          # Core LangGraph agent logic
├── sidekick_tools.py    # Tool integrations
├── sidekick.ipynb       # Experimental notebook
└── README.md
```

---

## 🚀 Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/operator-agent-sidekick.git
cd operator-agent-sidekick
```

### 2️⃣ Create Virtual Environment

```bash
python -m venv venv
```

Activate it:

**Mac/Linux**
```bash
source venv/bin/activate
```

**Windows**
```bash
venv\Scripts\activate
```

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔐 Environment Variables

Create a `.env` file in the root directory:

```
GROQ_API_KEY=your_groq_api_key
PUSHOVER_TOKEN=your_token (optional)
PUSHOVER_USER=your_user (optional)
```

---

## ▶️ Running the Application

```bash
python app.py
```

The Gradio interface will launch locally in your browser.

---

## 🧠 Example Usage

1. Enter your task in the message field  
2. Define success criteria  
3. Click **Go**  
4. The agent will:
   - Plan execution
   - Call tools if necessary
   - Generate response
   - Self-evaluate
   - Retry if needed
   - Return validated result  

---

## 🎯 What This Project Demonstrates

- Graph-based LLM orchestration  
- Autonomous tool usage  
- Self-evaluating AI systems  
- Multi-step reasoning loops  
- Production-style agent architecture  
- Clean separation of reasoning and validation  

This is a practical implementation of a modern **Operator-style autonomous AI assistant**.

---

## 🔮 Future Improvements

- Full Playwright browser automation  
- Vector database memory (RAG support)  
- Multi-user session handling  
- Dockerization and cloud deployment  
- Role-based multi-agent collaboration  

---

## 👤 Author

**Anubhav Srivastava**

GitHub: https://github.com/Anu-bhav-Sri  
LinkedIn: https://linkedin.com/in/anubhav172  

---

⭐ If you found this project useful, consider giving it a star!
