# Quick Start Guide

Get AI Data Labs up and running in 5 minutes.

## 🚀 Quick Start (Local Development)

### Prerequisites
- Python 3.10+
- Node.js 18+ (optional, for frontend)
- Docker (optional, for containerization)

### Step 1: Clone the Repository
```bash
cd /root/.openclaw/workspace/company
```

### Step 2: Backend Setup
```bash
cd backend

# Create virtual environment
python3 -m venv venv

# Activate it
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Start the API server
uvicorn app.main:app --reload
```

The API will be available at: http://localhost:8000

### Step 3: Test the API
```bash
# Health check
curl http://localhost:8000/health

# API docs (Swagger UI)
open http://localhost:8000/api/docs
```

### Step 4: Frontend Setup (Optional)
```bash
cd frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

The frontend will be available at: http://localhost:3000

---

## 🛠️ Autonomous Build

Run the build script to automate everything:
```bash
cd /root/.openclaw/workspace/company
./scripts/build.sh
```

This will:
- Check prerequisites
- Build backend
- Build frontend
- Build Docker images
- Run database migrations
- Start services

---

## 📖 Documentation

### Core Documents
- **PROJECT_SUMMARY.md** - Project overview and status
- **docs/COMPANY.md** - Business strategy and vision
- **docs/ARCHITECTURE.md** - Technical architecture
- **docs/ROADMAP.md** - 16-week execution plan

### API Documentation
- **Swagger UI:** http://localhost:8000/api/docs
- **ReDoc:** http://localhost:8000/api/redoc

---

## 🧪 Development

### Backend Development
```bash
cd backend
source venv/bin/activate

# Run with hot reload
uvicorn app.main:app --reload

# Run tests
pytest

# Format code
black app/
```

### Adding New API Endpoints
1. Create a new file in `backend/app/api/v1/`
2. Define your router:
```python
from fastapi import APIRouter

router = APIRouter()

@router.get("/endpoint")
async def my_endpoint():
    return {"message": "Hello"}
```
3. Register it in `backend/app/main.py`:
```python
from app.api.v1 import my_router
app.include_router(my_router.router, prefix="/api/v1/my", tags=["my"])
```

---

## 🐳 Docker Deployment

### Build Images
```bash
# Backend
docker build -f Dockerfile.backend -t aidatalabs/backend:latest .

# Frontend (when implemented)
docker build -f Dockerfile.frontend -t aidatalabs/frontend:latest .
```

### Run with Docker Compose
```bash
docker-compose up -d
```

---

## 📊 Next Steps

### For Developers
1. **Review Architecture:** Read `docs/ARCHITECTURE.md`
2. **Understand Roadmap:** Read `docs/ROADMAP.md`
3. **Pick a Task:** Check `PROJECT_SUMMARY.md` for current priorities
4. **Start Coding:** Follow the development guide above

### For Business
1. **Review Strategy:** Read `docs/COMPANY.md`
2. **Check Progress:** Review `PROJECT_SUMMARY.md`
3. **Plan Next Steps:** Follow the roadmap timeline
4. **Contact Founder:** me@duyet.net for partnership opportunities

---

## 🆘 Troubleshooting

### Common Issues

**Python version error:**
```bash
# Check Python version
python3 --version

# Install Python 3.10+ if needed
```

**Port already in use:**
```bash
# Check what's using port 8000
lsof -i :8000

# Kill the process
kill -9 <PID>

# Or use a different port
uvicorn app.main:app --port 8001
```

**Module not found:**
```bash
# Reinstall dependencies
pip install -r requirements.txt --force-reinstall
```

---

## 📞 Support

- **Documentation:** /docs
- **API Docs:** /api/docs
- **Issues:** GitHub Issues (coming soon)
- **Email:** hello@aidatalabs.ai

---

**Happy building! 🚀**
