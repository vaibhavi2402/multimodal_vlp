# Multimodal Vision-Language Pipeline (FastAPI + React)

This project is a **multimodal vision-language pipeline** built using **FastAPI** for the backend and **React** for the frontend. It combines **computer vision** and **natural language processing** to support:

- 🖼️ **Image Captioning** → Generate natural language captions for images using BLIP.
- ❓ **Visual Question Answering (VQA)** → Ask questions about an image and get contextual answers.
- 🔎 **Image ↔ Text Retrieval** → Retrieve images from a dataset using text queries with CLIP embeddings.

The project is structured into two parts: a **FastAPI backend** providing REST APIs, and a **React frontend** offering a user-friendly interface.

---

## 📂 Project Structure
```
multimodal_vlp/
├── backend/
│   ├── app.py              # FastAPI app with REST endpoints
│   ├── pipeline.py         # VisionLanguagePipeline class (load models, inference)
│   ├── utils.py            # helper functions (image loading, embedding store)
│   ├── requirements.txt
│   └── Dockerfile
│
├── frontend/
│   ├── package.json
│   ├── src/
│   │   ├── App.jsx         # React frontend
│   │   ├── components/     # Components: Captioning, VQA, Retrieval
│   │   └── api.js          # Axios API helpers
│   └── public/
│
└── README.md
```

---

## ⚙️ Installation Guide

### 🔹 Backend (FastAPI)
1. Navigate to the backend folder:
   ```bash
   cd backend
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate   # Linux/Mac
   .\.venv\Scripts\activate   # Windows
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the backend server:
   ```bash
   uvicorn app:app --reload --host 0.0.0.0 --port 8000
   ```

Backend will be available at: **http://localhost:8000**

---

### 🔹 Frontend (React)
1. Navigate to the frontend folder:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

Frontend will be available at: **http://localhost:5173**

---

## 🚀 Usage
- Open the frontend in your browser.
- **Captioning**: Upload an image → get a generated caption.
- **VQA**: Upload an image + ask a question → get an answer.
- **Retrieval**: Enter a text query → retrieve the most relevant images.

---

## 🛠️ Technologies Used
- **Backend**: FastAPI, Transformers (Hugging Face), PyTorch
- **Frontend**: React, Axios, Vite

---

## 📌 Notes
- Pre-trained models (BLIP, CLIP) are automatically downloaded from Hugging Face on first run.
- For large-scale retrieval, embeddings can be indexed using FAISS or another vector database.
- Dockerfiles are included for containerized deployment.
