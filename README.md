# Reflection AI Agent for Self-Improving LLM System

An implementation of the **Reflection Design Pattern** for Agentic AI. This project demonstrates a self-correcting loop where a **Generator** LLM creates Python code, and a **Critic** LLM evaluates it against a quality checklist, triggering iterative revisions until high-quality code is achieved.

##  Key Features
* **Dual-Role Architecture**: Implements specialized System Prompts for **Generator** and **Critic** roles.
* **Multi-Round Iteration**: A feedback loop that continues until the critic approves or a maximum round limit is reached.
* **Provider Agnostic**: Supports both **Groq (Llama-3.1-8b)** and **Ollama**, proving the pattern works independently of the LLM provider.
* **FastAPI Integration**: Provides a structured `POST /reflect` endpoint for real-time interaction.
* **Domain-Specific Critique**: The Critic uses a 5-point checklist: 
    1. Correctness 
    2. Edge Cases 
    3. Readability 
    4. Efficiency 
    5. Security.

## Architecture
    ┌──────────────┐
    │  User Input  │
    └──────┬───────┘
           │
    ┌──────▼───────┐
    │  Generator   │  → Generates Python Code
    └──────┬───────┘
           │
    ┌──────▼───────┐
    │   Critic     │  → Evaluates using checklist
    └──────┬───────┘
           │
    ┌──────▼───────┐
    │  Revision    │
    └──────┬───────┘
           │
    (Loop until approved or max rounds)

    
---

## ⚙️ Tech Stack

- **Backend:** FastAPI  
- **Language:** Python  
- **LLMs:** Groq (llama-3.1-8b-instant), Ollama  
- **Validation:** Pydantic  
- **Workflow Automation:** n8n  

---

## 📡 API Usage

### Endpoint
# Create the virtual environment
python -m venv venv

# Activate the environment (Windows PowerShell)
.\venv\Scripts\Activate.ps1

#install dependencies
pip install -r requirements.txt

#Groq Screenshots
<img width="1121" height="741" alt="Screenshot 2026-04-30 193000" src="https://github.com/user-attachments/assets/38dc73a4-2b0b-48b9-b9cd-2fac86aa781e" />
<img width="1431" height="740" alt="Screenshot 2026-04-30 192532" src="https://github.com/user-attachments/assets/463afd4a-e211-441d-ac10-2cc30aabe6c2" />
<img width="1171" height="590" alt="Screenshot 2026-04-30 192548" src="https://github.com/user-attachments/assets/d49bc3eb-bc8a-4244-ba51-57ecd025f5c9" />
<img width="1057" height="600" alt="Screenshot 2026-04-30 192948" src="https://github.com/user-attachments/assets/3fc27e51-9318-49ea-b24e-e127526f2df3" />


#Ollama Screenshots
<img width="1756" height="770" alt="Screenshot 2026-04-30 192832" src="https://github.com/user-attachments/assets/ef2edb06-b54f-4b58-a6fe-cd24c666c934" />
<img width="1662" height="675" alt="Screenshot 2026-04-30 192845" src="https://github.com/user-attachments/assets/6104c2a1-2c1a-44fb-b9e2-6f11f0a1f760" />
<img width="1185" height="729" alt="Screenshot 2026-04-30 193205" src="https://github.com/user-attachments/assets/8ef6002b-5945-42fa-99f8-49d006f40e75" />
<img width="1235" height="769" alt="Screenshot 2026-04-30 193220" src="https://github.com/user-attachments/assets/e8b8eb1c-aeb4-4ced-99a2-8a2d629a87fc" />










