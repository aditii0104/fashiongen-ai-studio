# FashionGen AI Studio 👗✨

A full-stack AI image generation platform tailored for fashion e-commerce. This studio allows users to upload garment or outfit images and generate high-fidelity, creative fashion editorial shots while strictly preserving the design, texture, and structural consistency of the original apparel.

## 🚀 Key Features

- **Outfit Consistency Engine**: Hardcoded backend prompt constraints and negative prompt loops that lock down garment structure, cuts, stitching, and design patterns, preventing AI hallucinations.
- **Dual-Model Architecture**: Built to handle enterprise production via Google Cloud's **Vertex AI (Nano Banana 2)** while maintaining an automated, live secondary pipeline using Google AI Studio's modern **Gemini (Imagen 3)** engine.
- **Robust Fault Tolerance & Graceful Degradation**: Features a fully managed error-handling architecture (`try/except` fallbacks) that seamlessly switches to a custom **"Simulated Mode"** when encountering cloud authentication, regional restrictions, or billing constraints—ensuring zero downtime for the user interface.
- **Secure Backend Middleman**: Avoids the critical vulnerability of exposing high-privilege API keys on the frontend by processing prompt generation, schema validation, and secure network requests through an isolated Python background server.

---

## 🛠️ Tech Stack

### Frontend (User Interface)
- Modern, semantic **HTML5**, **CSS3**, and asynchronous **JavaScript (ES6+)**
- Dynamic DOM manipulation for multi-image batch uploads and interactive output galleries
- Tabbed view management for "Output Gallery", "Prompt Preview", and "Consistency Check"

### Backend (API Server)
- **Python** - **FastAPI**: Asynchronous, high-performance web framework for managing multi-part form payloads
- **Uvicorn**: ASGI server implementation for lightning-fast local hosting
- **Pydantic**: Strict data validation and automated HTTP error generation

### AI Ecosystem
- **Google GenAI SDK** (`google-genai`): Utilizing `imagen-3.0-generate-001` for direct AI Studio integrations
- **Vertex AI SDK**: Rigged for production deployment utilizing `nano-banana-2`

---

## ⚙️ Architecture & Local Setup

### 1. Prerequisites
Ensure you have Python installed on your machine.

### 2. Installation
Clone the repository and install the production dependencies:
```bash
pip install fastapi uvicorn python-dotenv google-genai vertexai watchfiles
