# InfiniLearn

AI-Powered PDF Analysis and Knowledge Management Mobile Application.

> **Status:** Phase 1 — ~30% Progress (Prototype). Not the final version.

## What it does

1. User uploads a PDF from the Flutter app.
2. Backend (FastAPI) extracts text from the PDF using PyMuPDF.
3. KeyBERT (pre-trained) detects the top topics in the text.
4. A pre-trained Hugging Face model (BART/T5) generates a short summary.
5. Results are stored in SQLite (`PDFs` and `Topics` tables).
6. The app retrieves and lists saved topics/summaries.

Future phases (not in this milestone): Text-to-Speech, web information retrieval, authentication.

## Tech Stack

| Layer          | Tool                                  |
|----------------|----------------------------------------|
| Mobile App     | Flutter / Dart                        |
| Backend API    | Python + FastAPI                      |
| PDF Extraction | PyMuPDF                               |
| Topic Detection| KeyBERT                               |
| Summarization  | Hugging Face Transformers (BART/T5)   |
| Database       | SQLite                                |
| Data Handling  | NumPy, Pandas                         |
| Visualization  | Matplotlib                            |

## Project Structure

```
InfiniLearn/
├── frontend/          # Flutter mobile app
├── backend/           # FastAPI backend (API, routers, services)
├── ai/                # AI scripts: text extraction, topic detection, summarization
├── database/          # SQLite schema and seed scripts
├── docs/              # Architecture notes, API docs
├── assets/            # Shared assets (icons, sample PDFs, images)
├── README.md
├── requirements.txt
└── .gitignore
```

## Team

| Member  | Responsibility                                  |
|---------|--------------------------------------------------|
| Ashik   | Project Lead, GitHub Management, Backend & DB Integration |
| Member 2| Flutter UI, Navigation                          |
| Member 3| PDF Upload, PDF Viewer, File Management          |
| Member 4| AI Processing: Text Extraction, Topic Detection, Summarization |
| Member 5| Text-to-Speech Research, Web Info Research, Testing |

## Getting Started

### Backend
```bash
cd backend
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
pip install -r ../requirements.txt
uvicorn app.main:app --reload
```
API will run at `http://127.0.0.1:8000`. Docs at `http://127.0.0.1:8000/docs`.

### Frontend
```bash
cd frontend
flutter pub get
flutter run
```

## Milestone 1 Scope (this delivery)

- [x] Project & folder structure
- [ ] Flutter app: Splash, Home, Upload, PDF List screens + navigation
- [ ] FastAPI skeleton with routers (upload, extract, topics, summary)
- [ ] SQLite schema (PDFs, Topics tables)
- [ ] PyMuPDF text extraction service
- [ ] KeyBERT topic detection service
- [ ] Hugging Face summarization service
- [ ] End-to-end demo script
