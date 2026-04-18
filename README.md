# 🦁 Zoo Tour Guide Agent

<p align="center">
  <img src="https://img.shields.io/badge/Google_ADK-4285F4?style=for-the-badge&logo=google&logoColor=white" />
  <img src="https://img.shields.io/badge/Gemini_API-8E44AD?style=for-the-badge&logo=google&logoColor=white" />
  <img src="https://img.shields.io/badge/Cloud_Run-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Live-Demo-brightgreen?style=for-the-badge" />
</p>

<p align="center">
  A domain-specific AI agent that acts as an interactive zoo tour guide — built with Google's Agent Development Kit (ADK), powered by the Gemini API, and deployed live on Google Cloud Run.
</p>

<p align="center">
  🔗 <strong><a href="https://zoo-tour-guide-779830767021.europe-west1.run.app/">Try the Live Demo →</a></strong>
</p>

---

## 📌 What It Does

The Zoo Tour Guide Agent is a conversational AI agent that answers questions about zoo animals, exhibits, and tours. It demonstrates a complete agent deployment pipeline — from local development using Google ADK to a publicly accessible cloud-hosted service.

Ask it things like:
- *"Which animals are in the African Savanna exhibit?"*
- *"Tell me about the feeding schedule for penguins."*
- *"What's the best route to see the big cats?"*

---

## 🏗️ Architecture

```
User Request
     │
     ▼
Google Cloud Run (europe-west1)
     │
     ▼
  agent.py  ──► Google ADK Agent
                     │
                     ▼
               Gemini API (LLM)
                     │
                     ▼
            Domain-specific response
            (Zoo tour knowledge)
```

The agent is scoped to a single, clearly defined task — zoo tour guidance — making it a clean example of a **domain-specific AI agent** rather than a general-purpose chatbot.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Agent Framework | Google Agent Development Kit (ADK) |
| Language Model | Gemini API |
| Deployment | Google Cloud Run |
| Language | Python 3.11+ |
| Region | `europe-west1` |

---

## 📁 Project Structure

```
zoo_guide_agent/
├── agent.py           # Core agent definition (ADK agent + tools)
├── __init__.py        # Package init
├── requirements.txt   # Python dependencies
├── .env               # Environment variables (not committed — see setup)
└── README.md
```

---

## 🚀 Running Locally

### Prerequisites

- Python 3.11+
- A Google Cloud project with Gemini API enabled
- [Google ADK](https://google.github.io/adk-docs/) installed

### 1. Clone the repo

```bash
git clone https://github.com/Proyanshi/zoo_guide_agent.git
cd zoo_guide_agent
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Set up environment variables

Create a `.env` file in the root (never commit this):

```env
GOOGLE_API_KEY=your_gemini_api_key_here
GOOGLE_CLOUD_PROJECT=your_gcp_project_id
```

### 4. Run the agent locally

```bash
adk run .
```

The ADK dev UI will open in your browser at `http://localhost:8000`.

---

## ☁️ Deploying to Google Cloud Run

### 1. Authenticate with Google Cloud

```bash
gcloud auth login
gcloud config set project YOUR_PROJECT_ID
```

### 2. Deploy using ADK

```bash
adk deploy cloud_run \
  --project=YOUR_PROJECT_ID \
  --region=europe-west1 \
  --service-name=zoo-tour-guide
```

The ADK handles containerisation and Cloud Run deployment automatically.

---

## 💡 Key Concepts Demonstrated

- **Domain-specific agent design** — scoping an LLM agent to a single task domain for reliability
- **Google ADK agent structure** — using `agent.py` and `__init__.py` following ADK conventions
- **Cloud Run deployment** — containerised, serverless, auto-scaling deployment on GCP
- **Gemini API integration** — leveraging Gemini as the underlying language model via ADK

---

## 🌱 What I Learned

This project was built as part of my exploration of the **Google Cloud Arcade** program and Google's Agent Development Kit. It focuses on understanding:
- How to structure an agent project using Google ADK conventions
- How to deploy a Python-based AI agent to a production cloud environment
- The workflow from local `adk run` to live Cloud Run URL

---

## 📫 Author

**Priyanshi Chaudhary**
- 💼 [LinkedIn](https://www.linkedin.com/in/priyanshi-chaudhary-466508328)
- 🏅 [Google Skills Profile](https://www.skills.google/public_profiles/cc359b71-f029-470d-9680-3b25471ce990)
- 🐙 [GitHub](https://github.com/Proyanshi)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
