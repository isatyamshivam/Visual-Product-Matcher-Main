# Visual Product Matcher - AI Powered Search



An AI-powered visual product search system that enables users to find similar products by uploading images or providing URLs. Built with modern web technologies and deep learning for accurate visual similarity matching.This is the main repository that contains both the frontend and backend as submodules.



[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue)](https://github.com/isatyamshivam/Visual-Product-Matcher-Main)## Project Structure

[![FastAPI](https://img.shields.io/badge/FastAPI-Backend-green)](https://github.com/isatyamshivam/Visual-Product-Matcher-Backend)

[![React](https://img.shields.io/badge/React-Frontend-blue)](https://github.com/isatyamshivam/Visual-Product-Matcher-Frontend)```

Visual-Product-Matcher-Main/

## 🎯 Overview├── backend/          # Backend API (Python/Flask)

├── frontend/         # Frontend Application (React/Next.js)

Visual Product Matcher is an end-to-end machine learning application that helps users discover visually similar products from a catalog. Simply upload an image or paste a URL, and the system returns ranked results based on visual similarity scores using state-of-the-art deep learning embeddings.└── README.md

```

**Live Demo:** [Frontend URL] | **API Docs:** [Backend URL/docs]

## Getting Started

---

### Clone the Repository with Submodules

## 📋 Approach (Technical Summary)

To clone this repository along with all submodules, use:

### Core Architecture

- **Deep Learning Model**: Leveraged **MobileNetV2** (ImageNet pre-trained) for lightweight, efficient image embedding extraction with minimal memory footprint (~500MB), ideal for free-tier deployments```bash

- **Similarity Search**: Implemented **cosine similarity** using scikit-learn for fast vector comparison between query images and pre-computed catalog embeddingsgit clone --recurse-submodules https://github.com/isatyamshivam/Visual-Product-Matcher-Main.git

- **Backend Framework**: Built RESTful API with **FastAPI** featuring automatic OpenAPI documentation, async support, and robust error handling with request logging```

- **Frontend Stack**: Developed responsive UI using **Vite + React + TypeScript + Tailwind CSS** with drag-and-drop upload, URL input, adjustable similarity threshold slider, and real-time preview

Or if you've already cloned the repository without submodules:

### Data Pipeline

- **Preprocessing Script**: Created `build_embeddings.py` to automate catalog bootstrapping—downloads missing images, validates formats (JPEG/PNG/WebP), computes embeddings in batches, and exports aligned metadata to NumPy arrays and Excel```bash

- **Image Processing**: Standardized input pipeline with validation (size, format, corruption checks), resizing to model dimensions (224×224), and normalization matching ImageNet statisticsgit submodule update --init --recursive

- **Static Asset Serving**: Configured FastAPI to serve product images from `/static` endpoint with absolute URL construction for reliable frontend display```



### Deployment Strategy### Update Submodules

- **Split Architecture**: Designed for **backend on Railway/Render** (Docker containerized with thread limiting: `OMP_NUM_THREADS=2`) and **frontend on Vercel** (static build with CDN) to avoid serverless size constraints

- **Performance Optimization**: Implemented cold-start mitigation (first request in 30-60s), warm response caching (1-3s), and reduced TensorFlow logging (`TF_CPP_MIN_LOG_LEVEL=2`)To pull the latest changes from all submodules:

- **Environment Configuration**: Utilized environment variables (`VITE_API_URL`, `ALLOWED_ORIGINS`) for flexible cross-platform deployment with health check endpoints

```bash

### User Experiencegit submodule update --remote --merge

- **Intuitive Interface**: Designed clean UI with loading skeletons, responsive product cards, lazy-loaded images, and default "show all" threshold (0%) to prevent empty results```

- **Error Resilience**: Implemented comprehensive validation for file uploads, URL fetches, and API responses with user-friendly error messages

- **Docker Compose**: Provided local development setup coordinating both services—backend on `:8000`, frontend on `:3000` with hot-reload enabled## Submodules



### Code Quality- **Backend**: [Visual-Product-Matcher-Backend](https://github.com/isatyamshivam/Visual-Product-Matcher-Backend.git)

- **Repository Hygiene**: Maintained clean separation of concerns with modular backend utilities (embedding, preprocessing, similarity), TypeScript strict mode on frontend, and comprehensive documentation (README, ARCHITECTURE.md, DEPLOYMENT.md)- **Frontend**: [Visual-Product-Matcher-Frontend](https://github.com/isatyamshivam/Visual-Product-Matcher-Frontend.git)

- **CORS Configuration**: Enabled secure cross-origin requests with configurable allowed origins for production and development environments

## Setup Instructions

---

### Backend Setup

## 🏗️ Project Structure

```bash

This is the main repository containing both frontend and backend as **Git submodules**:cd backend

# Follow the backend README for setup instructions

``````

Visual-Product-Matcher-Main/

├── backend/                 # FastAPI Backend (Submodule)### Frontend Setup

│   ├── app/

│   │   ├── main.py         # FastAPI application entry point```bash

│   │   └── utils/          # Embedding, preprocessing, similarity modulescd frontend

│   ├── data/# Follow the frontend README for setup instructions

│   │   ├── products.csv    # Product catalog```

│   │   ├── embeddings.npy  # Pre-computed embeddings

│   │   └── valid_products.xlsx## Development

│   ├── scripts/

│   │   └── build_embeddings.py  # Catalog bootstrap scriptFor detailed setup and development instructions, please refer to the README files in each submodule:

│   ├── static/images/      # Product images served via /static- Backend: `backend/README.md`

│   └── requirements.txt    # Python dependencies- Frontend: `frontend/README.md`

│

├── frontend/               # React Frontend (Submodule)## License

│   ├── src/

│   │   ├── components/     # React componentsSee individual submodule repositories for license information.

│   │   ├── lib/           # Utilities
│   │   └── App.tsx        # Main application
│   ├── package.json       # Node dependencies
│   └── vite.config.ts     # Vite configuration
│
├── .gitmodules            # Submodule configuration
└── README.md              # This file
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** 20+ and npm
- **Python** 3.11+
- **Git** for cloning submodules
- **(Optional)** Docker 24+ for containerized deployment

### 1️⃣ Clone Repository with Submodules

```bash
# Clone with all submodules
git clone --recurse-submodules https://github.com/isatyamshivam/Visual-Product-Matcher-Main.git
cd Visual-Product-Matcher-Main

# Or if already cloned without submodules
git submodule update --init --recursive
```

### 2️⃣ Backend Setup

```bash
cd backend

# Install Python dependencies
pip install -r requirements.txt

# Build embeddings (required before first run)
python scripts/build_embeddings.py

# Start FastAPI server
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

**Backend API:** `http://localhost:8000`  
**API Docs:** `http://localhost:8000/docs`

### 3️⃣ Frontend Setup

```bash
cd frontend

# Install Node dependencies
npm install

# Configure API URL
echo "VITE_API_URL=http://localhost:8000" > .env

# Start Vite dev server
npm run dev
```

**Frontend:** `http://localhost:5173`

### 4️⃣ Docker Setup (Optional)

```bash
# From project root
docker compose up -d --build

# Frontend: http://localhost:3000
# Backend: http://localhost:8000
```

---

## 🔗 Submodules

- **Backend Repository**: [Visual-Product-Matcher-Backend](https://github.com/isatyamshivam/Visual-Product-Matcher-Backend)
- **Frontend Repository**: [Visual-Product-Matcher-Frontend](https://github.com/isatyamshivam/Visual-Product-Matcher-Frontend)

### Update Submodules

```bash
# Pull latest changes from all submodules
git submodule update --remote --merge
```

---

## 🌐 Deployment

### Recommended Architecture

```
User Browser → Vercel (Frontend) → Railway/Render (Backend) → TensorFlow + MobileNetV2
```

### Backend Deployment (Railway/Render)

**Platform:** Railway or Render with Docker  
**Configuration:**
- Root Directory: `backend`
- Start Command: `uvicorn app.main:app --host 0.0.0.0 --port 8000`
- Health Check: `/api/health`
- Port: `8000`

**Environment Variables:**
```env
PORT=8000
PYTHONUNBUFFERED=1
TF_CPP_MIN_LOG_LEVEL=2
OMP_NUM_THREADS=2
TF_NUM_INTRAOP_THREADS=2
TF_NUM_INTEROP_THREADS=2
ALLOWED_ORIGINS=*
```

### Frontend Deployment (Vercel)

**Platform:** Vercel  
**Configuration:**
- Framework Preset: Vite
- Build Command: `npm run build`
- Output Directory: `dist`

**Environment Variable:**
```env
VITE_API_URL=https://your-backend-url.railway.app
```

---

## 📚 Documentation

For detailed information, refer to documentation in the backend submodule:

- **[ARCHITECTURE.md](backend/ARCHITECTURE.md)** - System design and components
- **[DEPLOYMENT.md](backend/DEPLOYMENT.md)** - Deployment guide for all platforms
- **[QUICK_START.md](backend/QUICK_START.md)** - Fast deployment walkthrough
- **[Documentation.md](backend/Documentation.md)** - Comprehensive technical documentation

---

## 🛠️ Technology Stack

### Backend
- **FastAPI** - Modern async web framework
- **TensorFlow** - Deep learning inference
- **MobileNetV2** - Lightweight CNN for embeddings
- **scikit-learn** - Cosine similarity computation
- **Uvicorn** - ASGI server
- **Pandas/NumPy** - Data processing

### Frontend
- **React 18** - UI library
- **TypeScript** - Type safety
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Utility-first styling
- **Axios** - HTTP client
- **Lucide React** - Icon library

---

## 📊 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/health` | GET | Health check |
| `/api/products` | GET | List all catalog products |
| `/api/categories` | GET | Get available categories |
| `/api/search` | POST | Search by image (file or URL) |
| `/static/*` | GET | Serve product images |

---

## ✨ Features

✅ **Image Upload** - Drag-and-drop or file picker (JPEG, PNG, WebP)  
✅ **URL Search** - Paste image URLs for remote image matching  
✅ **Adjustable Threshold** - Control similarity sensitivity (0-100%)  
✅ **Real-time Preview** - See uploaded image before search  
✅ **Responsive Design** - Works on desktop, tablet, and mobile  
✅ **Loading States** - Skeleton loaders for better UX  
✅ **Error Handling** - User-friendly error messages  
✅ **Docker Support** - One-command local setup  

---

## 🤝 Contributing

Contributions are welcome! Please refer to individual submodule repositories for contribution guidelines.

---

## 📄 License

This project is open source. See individual submodule repositories for specific license information.

---

## 👨‍💻 Author

**Satyam Shivam**  
- GitHub: [@isatyamshivam](https://github.com/isatyamshivam)
- Backend: [Visual-Product-Matcher-Backend](https://github.com/isatyamshivam/Visual-Product-Matcher-Backend)
- Frontend: [Visual-Product-Matcher-Frontend](https://github.com/isatyamshivam/Visual-Product-Matcher-Frontend)

---

## 🙏 Acknowledgments

- MobileNetV2 architecture by Google Research
- FastAPI framework by Sebastián Ramírez
- React ecosystem and community

---

**⭐ If you find this project helpful, please consider giving it a star!**
