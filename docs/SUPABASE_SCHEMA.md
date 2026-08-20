# Supabase Database Schema

## Tables

### users (Supabase Auth)
Automatically managed by Supabase

### devices
```sql
CREATE TABLE devices (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES auth.users(id),
  device_id TEXT UNIQUE,
  device_name TEXT,
  device_type TEXT,
  created_at TIMESTAMP
);
```

### scans
```sql
CREATE TABLE scans (
  id UUID PRIMARY KEY,
  device_id TEXT REFERENCES devices(device_id),
  security_score INTEGER,
  threats_found INTEGER,
  risks JSONB,
  created_at TIMESTAMP
);
```

### threat_checks
```sql
CREATE TABLE threat_checks (
  id UUID PRIMARY KEY,
  device_id TEXT,
  url TEXT,
  is_safe BOOLEAN,
  threats TEXT[],
  created_at TIMESTAMP
);
```

### chat_messages
```sql
CREATE TABLE chat_messages (
  id UUID PRIMARY KEY,
  conversation_id UUID,
  device_id TEXT,
  user_message TEXT,
  assistant_response TEXT,
  created_at TIMESTAMP
);
```

### families
```sql
CREATE TABLE families (
  id UUID PRIMARY KEY,
  admin_id UUID REFERENCES auth.users(id),
  name TEXT,
  invite_code TEXT UNIQUE,
  created_at TIMESTAMP
);
```

### family_devices
```sql
CREATE TABLE family_devices (
  id UUID PRIMARY KEY,
  family_id UUID REFERENCES families(id),
  device_id TEXT,
  owner_name TEXT,
  joined_at TIMESTAMP
);
```

### family_alerts
```sql
CREATE TABLE family_alerts (
  id UUID PRIMARY KEY,
  family_id UUID REFERENCES families(id),
  device_id TEXT,
  severity TEXT,
  message TEXT,
  created_at TIMESTAMP
);
```

## Setup

1. Create Supabase project
2. Go to SQL Editor
3. Run the table creation queries above
4. Enable Row Level Security (RLS) on all tables
