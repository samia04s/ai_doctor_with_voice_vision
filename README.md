# 🧠 AI_Therapist – AI Mental Health Therapist (Agentic AI)

SafeSpace is an **agentic AI-powered mental health support system** designed to provide **empathetic, supportive, and safety-aware conversations**.  
It combines **Groq LLMs**, **LangGraph ReAct agents**, **FastAPI**, **Streamlit**, **Twilio**, and **Geo-based therapist discovery** into a single, production-ready architecture.

> ⚠️ **Disclaimer**: This project is for educational and experimental purposes only. It does **not** replace professional mental health care.

---

## 🌟 Key Features

### 💬 Empathetic AI Therapist
- Therapist persona: **Dr. Emily Hartman**
- Emotionally attuned, non-judgmental responses
- Strengths-focused guidance
- Open-ended questioning to explore root causes

### 🤖 Agentic AI (ReAct Architecture)
- Built using **LangGraph ReAct Agent**
- Dynamic decision-making based on user intent
- Tools are invoked only when required

### 🚨 Crisis Detection & Emergency Support
- Detects signs of:
  - Suicidal ideation
  - Self-harm intent
  - Mental health emergencies
- Automatically triggers **Twilio emergency call tool**

### 📍 Nearby Therapist Finder
- Uses **Geoapify + Geopy**
- Finds real mental health professionals near the user’s location
- Returns names, addresses, and contact details

### 🌐 Multi-Channel Support
- **Web UI** via Streamlit
- **WhatsApp integration** via Twilio (TwiML)

---

## 🏗️ Project Architecture

AI Mental Health Therapist/

├── backend/

│   ├── ai_agent.py         # LangGraph-based AI agent + tools (LLM, emergency call, therapist finder)

│   ├── config.py           # API keys and configuration (not shown here; you create it)

│   ├── main.py             # FastAPI backend (JSON /ask + Twilio WhatsApp /whatsapp_ask)

│   ├── tools.py            # Low-level tool implementations (MedGemma, Twilio call, etc.)

│   └── test_location_tool.py  # Tests/examples for the location tool

├── frontend.py              # Streamlit chat UI (web client) talking to FastAPI backend

├── pyproject.toml           # Project metadata and Python dependencies (managed with uv)'

└── README.md                # Main project README

---

## 🔁 Agent Tools Overview

| Tool Name | Purpose |
|---------|--------|
| `ask_mental_health_specialist` | Empathetic therapeutic conversation |
| `find_nearby_therapists_by_locations` | Locate nearby professionals |
| `emergency_call_tool` | Trigger emergency call via Twilio |

The agent automatically decides **which tool to use and when**.

---

## 🚀 How It Works (Flow)

1. User sends a message (Web / WhatsApp)
2. Message enters **LangGraph ReAct Agent**
3. Agent reasons about intent
4. Appropriate tool is invoked
5. Final response is returned safely and empathetically

---

## 🧠 Tech Stack

### 🤖 AI & LLM
- **Groq LLM** – `openai/gpt-oss-120b`
- **LangChain** – LLM orchestration
- **LangGraph** – Agentic AI (ReAct architecture)

### 🧩 Backend
- **FastAPI** – High-performance backend API
- **Uvicorn** – ASGI server

### 🎨 Frontend
- **Streamlit** – Interactive web interface

### 📡 Communication & Safety
- **Twilio** – WhatsApp messaging & emergency voice calls

### 📍 Location Intelligence
- **Geoapify API** – Nearby therapist discovery
- **Geopy** – Geocoding user locations

### 📦 Environment & Tooling
- **Python 3.10+**
- **uv** – Fast Python package & environment manager

### 🔐 Configuration
- **Environment variables / config.py** – Secure API key management
## 🔮 Future Improvements

### 1️⃣ Streaming Responses
- Enable token-by-token LLM streaming
- Show real-time typing in Streamlit
- Improve conversational flow

### 2️⃣ Multimodal Capabilities
- Image-based contextual understanding
- Voice input with speech-to-text
- Optional audio-based responses

### 3️⃣ Multi-Agent Architecture
- Specialized agents:
  - **Therapy Agent** – emotional support
  - **Safety Agent** – crisis detection
  - **Resource Agent** – therapist discovery
  - **Reflection Agent** – session insights
- Agent coordination via LangGraph

### 4️⃣ Long-Term Memory & Personalization
- Session-aware memory
- Personalized therapeutic responses

### 5️⃣ Production Readiness & Security
- Authentication and access control
- Rate limiting and monitoring



