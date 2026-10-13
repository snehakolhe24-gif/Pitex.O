# Pitex.O
A mobile Software Application

VOICE AI MOBILE APP
│
├── FRONTEND (REACT NATIVE)
│   │
│   ├── components
│   │   ├── MicButton.jsx
│   │   ├── TranscriptBox.jsx
│   │   └── AudioPlayer.jsx
│   │
│   ├── hooks
│   │   └── useRecorder.js
│   │
│   ├── services
│   │   └── api.js
│   │
│   └── App.jsx
│
└── BACKEND (DJANGO)
    │
    ├── manage.py
    ├── requirements.txt
    │
    ├── config
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    │
    ├── voice (app)
    │   ├── views.py
    │   ├── urls.py
    │   │
    │   └── services
    │       ├── stt_service.py       (Whisper STT)
    │       └── tts_service.py       (KittenTTS)
    │
    └── rag (app)
        ├── ingest.py                (Document chunking)
        ├── embeddings.py            (Text embeddings)
        ├── retriever.py             (Vector DB search)
        ├── llm.py                   (AI answer generation)
        └── pipeline.py              (Complete RAG flow)
