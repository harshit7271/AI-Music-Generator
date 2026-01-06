# 🎵 MelodyX: SaaS AI Music Generator

**MelodyX** is a full‑stack SaaS application that generates music from text prompts using cutting‑edge diffusion models and large language models. Built for scalability and recruiter‑ready polish, it combines **FastAPI** for backend orchestration, **React + Next.js** for frontend UI, **AWS S3** for audio storage, and **Modal** for cloud deployment.

---

##  Features
-  **Text‑to‑Music Generation** powered by ACE‑Step diffusion pipeline.
-  **FastAPI backend** with REST endpoints for music generation.
-  **React + Next.js frontend** with recruiter‑focused branding and polished UI.
-  **Modal cloud deployment** for reproducible, scalable inference.
-  **AWS S3 bucket integration** for storing and serving generated audio files.
-  Robust error handling and input validation for production‑grade UX.
-  Reproducible environment with pinned HuggingFace stack (`transformers`, `diffusers`, `peft`, `accelerate`, `torchcodec`).

---

##  Tech Stack
- **Frontend**: React, Next.js, TailwindCSS
- **Backend**: FastAPI, Python 3.12
- **ML Frameworks**: HuggingFace Transformers, Diffusers, PEFT, Accelerate
- **Audio**: Torch, Torchaudio, TorchCodec, SoundFile
- **Deployment**: Modal (serverless GPU inference)
- **Storage**: AWS S3 bucket
- **Utilities**: Pydantic, Requests, Safetensors

---

---

## ⚙️ Installation

### Backend
```bash
git clone https://github.com/harshit7271/AI-Music-Generator-SAAS.git
cd AI-Music-Generator-SAAS/backend
python -m venv .venv
.venv\Scripts\activate   # Windows
pip install -r requirements.txt
```
### Frontend
```bash
cd AI-Music-Generator-SAAS/frontend
npm install
npm run dev
```
### Running Locally
```bash
uvicorn main:app --reload
```
**Run the Next.js frontend:**
```bash
npm run dev
```

## API Usage
**Generate Music**
**Endpoint:** `POST /generate`

**Request:**
```
{
  "prompt": "lofi hip hop beats with jazz influence",
  "guidance_scale": 15,
  "num_inference_steps": 60
}
```

**Response:**
```
{
  "audio_url": "https://<your-s3-bucket>.s3.amazonaws.com/generated.wav",
  "duration": 30,
  "status": "success"
}
```

## Requirements
**Pinned versions for reproducibility:**
```
transformers==4.39.3
diffusers==0.29.0
peft==0.17.0
accelerate==0.30.0
pydantic
torch>=2.1.0
safetensors>=0.4.0
torch>=2.1.0
torchaudio>=2.1.0
torchcodec>=0.2.0
```

**Frontend dependencies `(in package.json)`:**
```
{
  "dependencies": {
    "next": "latest",
    "react": "latest",
    "react-dom": "latest",
    "tailwindcss": "latest",
    "axios": "latest"
  }
}
```


## Notes :
- Ensure CUDA is available for GPU acceleration, otherwise fallback to CPU.
- TorchCodec is required for saving audio with torchaudio.save.
- AWS S3 bucket must be configured with proper credentials for audio storage.
- Future warnings from HuggingFace libraries are safe to ignore but can be silenced.

## Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you’d like to change.

---