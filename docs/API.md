# GuardAI Backend API Documentation

## Base URL
```
http://localhost:5000  (Development)
https://guardai-api.example.com  (Production)
```

## Authentication
All requests must include JWT token:
```
Authorization: Bearer <supabase_jwt_token>
```

## Core Endpoints

### 1. Health Check
```
GET /health
```

### 2. App Scanner
```
POST /api/scan
Body: { device_id, apps: [...] }
Response: { security_score, threats_found, risks: [...] }
```

### 3. Threat Check (Web Protection)
```
POST /api/threat-check
Body: { url, device_id }
Response: { is_safe, threats: [...] }
```

### 4. AI Chat
```
POST /api/chat
Body: { message, device_id, conversation_id? }
Response: { conversation_id, response }

GET /api/chat/history/{conversation_id}
```

### 5. Security Score
```
GET /api/security-score/{device_id}
Response: { security_score, threats_blocked, score_breakdown }
```

### 6. Family Protection
```
POST /api/family/create
POST /api/family/join
GET /api/family/{family_id}/devices
GET /api/family/{family_id}/alerts
```

## Rate Limiting

- Scanning: 10 scans/hour per device
- Threat checks: 100 checks/hour
- Chat: 50 messages/hour
