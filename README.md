# AnalyzerGPT – Multi-Agent AI Data Analysis System

## 📌 Overview
AnalyzerGPT is an **AI-powered multi-agent system** built using **Microsoft Autogen** for automated dataset analysis.  
It enables users to upload CSV files and interact with them through a **chat-based interface**, where:  
- A **Data Analyzer Agent** generates Python code for queries.  
- A **Code Executor Agent** safely runs the code in a **Docker container**.  
- Results are returned as text, tables, or visualizations, ensuring accuracy and reproducibility.  

This project demonstrates the power of **LLMs, AI agents, and containerized execution** for building scalable, client-ready AI Proof of Concepts (POCs).

---

## 🚀 Features
- Multi-agent architecture (**Data Analyzer + Code Executor**)  
- **Autonomous code generation & execution** for dataset queries  
- **Safe execution in Docker sandbox** to protect the local system  
- **Streamlit UI** for interactive, chat-style data exploration  
- Support for **visual outputs** (tables, charts, graphs)  
- Extensible for custom datasets beyond Titanic (default example)  

---

## 🛠️ Tech Stack
- **Language**: Python  
- **Frameworks & Libraries**: Microsoft Autogen, Pandas, NumPy, Matplotlib  
- **Containerization**: Docker  
- **Frontend/Interface**: Streamlit  
- **Orchestration & Config**: Custom prompts, agents, and config files  

---

## 📂 Project Structure

AnalyzerGPT/
├── agents/                     # AI agent definitions
│   ├── Code_ExecutorAgent.py    # Executes generated Python code safely

│   ├── Data_AnalyzerAgent.py    # Generates analysis code from user queries
│
├── prompts/                    # Prompt templates for agents

│   ├── DataAnalyzerAgent_prompt.py

│   ├── CodeExecutorAgent_prompt.py
│
├── config/                     # Configuration files
│   ├── constants.py             # Project constants and paths
│   ├── docker_utils.py          # Docker helper functions
│   ├── openai_model_config.py   # OpenAI/LLM model configuration
│
├── models/                     # Placeholder for trained/custom models
│
├── team/                       # Agent team orchestration
│   ├── analyzer_gpt.py
│
├── main.py                     # Main entry point for running the system
├── streamlit_app.py            # Streamlit interface for chat-based interaction
├── requirements.txt            # Python dependencies
├── .env                        # API keys and environment variables
├── output1.lua                  # Example output/log file

---

## ⚙️ Setup & Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/AnalyzerGPT.git
   cd AnalyzerGPT
2. **Create a virtual environment (optional but recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate   # Mac/Linux
   venv\Scripts\activate      # Windows
3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
4. **Configure environment variables**
  Create a .env file in the project root.
  Add your keys (example):
   ```bash
    OPENAI_API_KEY=your_openai_key_here
5. **Run Docker (for safe execution)**
    ```bash 
   docker build -t analyzer-gpt .
   docker run -it analyzer-gpt
6. **Run the Streamlit app**
   ```bash
   streamlit run streamlit_app.py 
