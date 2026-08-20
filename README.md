# GuardAI - Mobile Phone Security App

A fullstack cross-platform mobile security application built with Flutter, Supabase, and Python.

## Features

- 🔒 **App Scanner & Risk Badges** - Scan installed apps with PackageManager
- 📊 **Security Score & Threats Blocked** - Real-time threat tracking
- 🌐 **Web Protection** - Phishing blocking via Google Safe Browsing API
- 🤖 **Ask GuardAI** - AI-powered security chat (OpenRouter/OpenAI/Anthropic)
- 👨‍👩‍👧‍👦 **Family Protection** - Multi-device management via Supabase
- ⚠️ **AI Threat Detection** - Heuristic-based malware detection

## Project Structure

```
guardai-mobile/
├── mobile/                 # Flutter mobile app
├── backend/                # Python backend server
├── docs/                   # Documentation
└── README.md              # This file
```

## Quick Start

### Prerequisites
- Flutter 3.0+
- Python 3.9+
- Supabase account
- API keys (Google Safe Browsing, OpenRouter/OpenAI/Anthropic)

### Mobile Setup
```bash
cd mobile
flutter pub get
flutter run
```

### Backend Setup
```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
python run.py
```

## Environment Variables

Create `.env` files with your API keys:

### Mobile: `mobile/.env`
```
SUPABASE_URL=your_supabase_url
SUPABASE_ANON_KEY=your_anon_key
BACKEND_URL=http://localhost:5000
```

### Backend: `backend/.env`
```
SUPABASE_URL=your_supabase_url
SUPABASE_SERVICE_KEY=your_service_key
GOOGLE_SAFE_BROWSING_API_KEY=your_api_key
OPENROUTER_API_KEY=your_api_key
OPENAI_API_KEY=your_api_key
ANTHROPIC_API_KEY=your_api_key
```

## Documentation

- [Mobile App Setup](./docs/MOBILE_SETUP.md)
- [Backend Setup](./docs/BACKEND_SETUP.md)
- [API Documentation](./docs/API.md)
- [Architecture](./docs/ARCHITECTURE.md)
- [Supabase Schema](./docs/SUPABASE_SCHEMA.md)

## License

MIT
