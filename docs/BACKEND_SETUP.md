# Backend Setup

## Prerequisites

- Python 3.9+
- pip

## Installation

### 1. Navigate to backend directory
```bash
cd backend
```

### 2. Create virtual environment

**Linux/Mac:**
```bash
python3 -m venv venv
source venv/bin/activate
```

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Environment setup

Create `backend/.env`:
```env
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_KEY=your_service_key
GOOGLE_SAFE_BROWSING_API_KEY=your_api_key
OPENROUTER_API_KEY=your_api_key
ENV=development
DEBUG=True
PORT=5000
```

### 5. Run the server
```bash
python run.py
```

Server starts at `http://localhost:5000`

## Deployment

### Railway.app (Recommended)
1. Push to GitHub
2. Connect repo to Railway
3. Add environment variables
4. Deploy

### Heroku
```bash
heroku create guardai-backend
heroku config:set SUPABASE_URL=...
git push heroku main
```

### Docker
```bash
docker build -t guardai-backend .
docker run -p 5000:5000 --env-file .env guardai-backend
```

## Troubleshooting

- **Module errors:** Ensure venv is activated
- **Connection errors:** Check .env credentials
- **Port in use:** Change PORT in .env or kill process
