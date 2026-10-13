# Pitex.O
A mobile Software Application

# 🎙️ VoiceAI – Voice-Based AI Assistant

## 📌 Project Overview

VoiceAI is an interactive voice-based assistant that allows users to ask questions using their voice or text. The application converts speech into text, searches relevant information from a knowledge base using a RAG-inspired retrieval process, displays an answer, and converts the response into speech.

> **Current status:** This is a frontend prototype. It uses browser speech features and keyword-based retrieval. A production RAG backend and an LLM are planned enhancements and are not yet connected.

## ✨ Features

- 🎤 Voice input using a microphone button
- 📝 Speech-to-text conversion (browser support required)
- 💬 Interactive question-and-answer interface
- 📚 Upload custom knowledge files in TXT and Markdown formats
- 🔍 Search uploaded documents using keyword-based retrieval
- 🔊 Text-to-speech for spoken responses
- 📋 Copy answers to the clipboard
- 📱 Responsive interface for desktop and mobile screens
- 🧠 Sample knowledge pack for testing

## 🛠️ Technologies Used

- HTML5
- CSS3
- JavaScript
- Web Speech API (browser-dependent speech recognition)
- Browser Speech Synthesis API
- Local keyword-based document retrieval

## 🏗️ System Architecture

```text
                         USER
                           |
                           v
               FRONTEND (HTML, CSS, JS)
                           |
                 +---------+---------+
                 |                   |
                 v                   v
          Microphone Input        Text Input
                 |
                 v
          Speech-to-Text
          (Web Speech API)
                 |
                 v
             User Query
                 |
                 v
        LOCAL RETRIEVAL PIPELINE
                 |
                 v
       Uploaded Knowledge Files
            (TXT / Markdown)
                 |
                 v
       Keyword-Based Retrieval
                 |
                 v
            Answer Text
                 |
                 v
          Text-to-Speech
       (Browser Speech Synthesis)
                 |
                 v
        DISPLAY TEXT + PLAY AUDIO
```

### 🔮 Planned Full RAG Architecture

```text
MOBILE / WEB FRONTEND
        |
        v
  Backend API (Django)
        |
        v
  Speech-to-Text (Whisper)
        |
        v
    User Question
        |
        v
    RAG Pipeline
        |
        +--> Query Embeddings
        |         |
        |         v
        |    Vector Database
        |         |
        |         v
        |   Relevant Documents
        |
        v
  LLM Answer Generation
        |
        v
     Answer Text
        |
        v
 Text-to-Speech (KittenTTS)
        |
        v
  Audio + Text Response
```

The planned full version can use a vector database such as ChromaDB, FAISS, or PostgreSQL with pgvector. An LLM such as Gemini can generate responses using retrieved context.

## 📂 Project Folder Structure

```text
voice-ai-assistant/
├── index.html       # Application interface
├── style.css        # Styling and responsive layout
├── app.js           # Voice controls, retrieval, and speech output
└── README.md        # Project documentation
```

### Planned Backend Folder Structure

```text
backend/
├── manage.py
├── requirements.txt
├── config/
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── voice/
│   ├── views.py
│   ├── urls.py
│   └── services/
│       ├── stt_service.py
│       └── tts_service.py
└── rag/
    ├── ingest.py
    ├── embeddings.py
    ├── retriever.py
    ├── llm.py
    └── pipeline.py
```

## ⚙️ How It Works

1. The user presses the microphone button or types a question.
2. If voice input is supported, the browser converts speech into text.
3. The app searches the uploaded knowledge files for relevant passages.
4. The retrieved text is shown as the answer.
5. The user can choose **Read Answer Aloud** to hear the response.
6. The user can upload or remove TXT and Markdown files at any time.

## 🚀 How to Run Locally

1. Download or clone this repository.
2. Open `index.html` in a modern browser. Chrome is recommended.
3. Click **Load Sample Knowledge** or upload your own `.txt` or `.md` files.
4. Ask a question by typing or using the microphone.
5. Click **Read Answer Aloud** to listen to the response.

Speech recognition may require microphone permission and may only work in supported browsers or secure contexts such as HTTPS or localhost. Text input remains available if voice recognition is unsupported.

## 🌐 Deploy on GitHub Pages

1. Create a GitHub repository, for example `voice-ai-assistant`.
2. Upload `index.html`, `style.css`, `app.js`, and `README.md` to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select the `main` branch and the `/ (root)` folder, then click **Save**.
6. Open the GitHub Pages URL after deployment completes.

## 🧩 Architecture Components

| Component | Responsibility |
|---|---|
| Frontend | Displays the interface, question input, and answer |
| Speech-to-Text | Converts voice into text using browser speech recognition |
| Knowledge Base | Holds the uploaded TXT and Markdown content in browser memory |
| Retrieval | Uses keyword matching to find relevant passages |
| Answer Display | Shows the selected passages as a response |
| Text-to-Speech | Reads the answer aloud using browser speech synthesis |
| Planned Django API | Will coordinate server-side processing in a future version |
| Planned RAG Pipeline | Will chunk documents, create embeddings, retrieve relevant context, and call an LLM |
| Planned Vector Database | Will store embeddings for semantic search |

## 🔮 Future Enhancements

- Integrate a Django backend and REST API.
- Use Whisper for speech-to-text conversion.
- Add document ingestion and chunking.
- Generate embeddings for uploaded documents.
- Connect a vector database such as ChromaDB or FAISS.
- Integrate an LLM such as Gemini for contextual answer generation.
- Integrate KittenTTS or another TTS service.
- Add conversation history, language selection, and improved error handling.
- Add secure file storage and authentication if needed.

## ⚠️ Limitations

- The current version uses keyword matching, not semantic vector search.
- The current version does not call an LLM, so it does not generate new AI answers.
- Speech recognition support varies by browser.
- Uploaded knowledge files remain in the current browser session and are not uploaded to a backend server.
- The Django, Whisper, KittenTTS, embeddings, vector database, and LLM components shown in the planned architecture are not yet implemented.

## 🔐 Security Note

Never commit API keys, passwords, access tokens, or other secrets to a public GitHub repository. Store backend secrets in environment variables.

## 🎯 Project Purpose

This project demonstrates a simple voice assistant interface and the core ideas behind combining speech interaction with document retrieval. It provides a foundation for extending the prototype into a full RAG-powered voice assistant.

## 📄 License

This project is intended for educational and learning purposes. Add a specific open-source license file if you want to formally define reuse and distribution terms.
