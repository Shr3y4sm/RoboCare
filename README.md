# AI-Powered Mental Health Chatbot

## Overview
This AI-powered chatbot is designed to assist users with mental health-related queries by leveraging advanced NLP, multilingual speech processing, and real-time data retrieval. The chatbot provides personalized, reliable, and accessible mental health support while ensuring user privacy.

## Tech Stack
- **Frontend:** React.js or Streamlit
- **Backend:** FastAPI for efficient request handling
- **Vector Database:** FAISS for fast and accurate information retrieval
- **LLM (Language Model):** Gemini API with RAG framework (LangChain) for context-aware responses
- **Multilingual Speech Processing:** Kokoro for text-to-speech and speech-to-text.

## Dataset
- Self help books and articles 
## Features
- **Mental Health Assistance:** Provides evidence-based responses to user queries.
- **Multimodal Capabilities:** Supports text and voice-based inputs.
- **Multilingual Support:** Enables voice-based interactions in multiple languages for wider accessibility.
- **Reliable Information:** Reduces misinformation by sourcing data from authoritative sources.
- **Context-Aware Responses:** Uses RAG to enhance the accuracy and personalization of responses.

## How to Run
1. **Clone the Repository**
   ```bash
   # RoboCare — AI-powered Mental Health Chatbot

   RoboCare is an experimental AI-powered chatbot that helps users with mental health related questions using retrieval-augmented generation (RAG), multilingual speech support, and a React frontend. This README explains how to run the app locally (backend + frontend), important environment variables, and where to look in the codebase.

   ## Key highlights
   - Conversational mental-health assistant (text + voice)
   - Retrieval using local vector store (FAISS) and RAG
   - FastAPI backend and React frontend

   ## Repository layout

   - `backend/` — FastAPI app and RAG/TTs helpers (contains `main.py`, `rag.py`, `tts.py`, `requirements.txt`)
   - `frontend/` — React app (created with Create React App)
   - `package.json` — root helper tasks (if any)

   ## Quick start (Windows PowerShell)

   1) Clone the repo

       git clone <repository-url>
       cd RoboCare

   2) Backend: create venv and install

       python -m venv .venv
       # PowerShell: activate
       .\.venv\Scripts\Activate.ps1
       pip install -r backend\requirements.txt

   3) Start the backend (from `backend/`)

       cd backend
       uvicorn main:app --reload --port 8000

   The backend will be available at http://localhost:8000 by default.

   4) Frontend: install and run (separate terminal)

       cd frontend
       npm install
       npm start

   The React app will open at http://localhost:3000 (CRA default).

   ## Environment variables

   The project may expect API keys or configuration for the LLM, TTS, or vector store. Examples (set these in PowerShell before starting the backend):

       $env:OPENAI_API_KEY = "your_api_key"
       $env:KOKORO_API_KEY = "your_kokoro_key"
       $env:FAISS_INDEX_PATH = "./data/faiss.index"

   Adjust names to match the actual variables used in `backend/` code. If a variable is missing or the backend raises an error, check `backend/*.py` for the exact names.

   ## Development notes

   - Backend entrypoint: `backend/main.py` (FastAPI app). If you change the host/port update the frontend proxy or configuration.
   - RAG helpers and index-loading are in `backend/rag.py`.
   - TTS / STT helpers are in `backend/tts.py`.

   ## Troubleshooting

   - If `uvicorn` is not found, run `pip install uvicorn` or use `python -m uvicorn main:app --reload`.
   - If the frontend cannot reach the backend, confirm the backend is running on port `8000` and CORS is configured in `main.py`.
   - For missing API keys, the backend will usually raise an exception at startup — check the console and set the required env vars.

   ## Tests

   There are no automated tests included yet. As a next step we can add unit tests for the backend endpoints and a small E2E test for the frontend.

   ## Contributing

   Contributions are welcome. Suggested small improvements:

   - Add environment variable documentation with exact variable names.
   - Add automated tests and CI (GitHub Actions).
   - Add example `.env.example` or a `docker-compose` file for local dev.

   When opening a PR, please include a short description and how to run your changes locally.

   ## License & attribution

   Specify a license in this repo (e.g., MIT) by adding a `LICENSE` file. If you want, I can add a suggested `LICENSE` file for you.

   ---

