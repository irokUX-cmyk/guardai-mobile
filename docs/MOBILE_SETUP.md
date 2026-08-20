# Mobile App Setup

## Prerequisites

- Flutter 3.0+
- Dart 3.0+
- Android SDK 21+ or iOS 11.0+

## Installation

### 1. Navigate to mobile directory
```bash
cd mobile
```

### 2. Get dependencies
```bash
flutter pub get
```

### 3. Generate code
```bash
flutter pub run build_runner build
```

### 4. Environment setup

Create `mobile/.env`:
```env
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_ANON_KEY=your_anon_key
BACKEND_URL=http://localhost:5000
```

### 5. Run
```bash
flutter run
```

## Building for Release

### Android
```bash
flutter build apk --release
flutter build appbundle --release
```

### iOS
```bash
flutter build ios --release
```

## Troubleshooting

- **SDK not found:** Run `flutter doctor`
- **Supabase error:** Verify .env credentials
- **Build issues:** Run `flutter clean` then `flutter pub get`
