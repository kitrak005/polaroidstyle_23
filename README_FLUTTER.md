# Retro Studio - Flutter Mobile App

AI-powered vintage Polaroid photo transformation mobile app built with Flutter.

## Features

- 📸 **Camera & Gallery** - Take photos or select from your gallery
- 🤖 **AI Transformation** - Uses Google Gemini 2.5 Flash to transform photos into vintage Polaroids
- 🎞️ **Authentic Polaroid Style** - Thick white borders, warm tones, film grain effects
- 💾 **Save to Gallery** - Download your Polaroid masterpieces
- 📱 **Cross-Platform** - Works on both Android and iOS

## Prerequisites

- Flutter SDK (>=3.0.0)
- Dart SDK
- Android Studio / Xcode (for emulators)
- A Google Gemini API key

## Setup

### 1. Install Dependencies

```bash
flutter pub get
```

### 2. Configure API Key

Create a `.env` file in the root directory:

```bash
cp .env.example .env
```

Edit `.env` and add your Gemini API key:

```
GEMINI_API_KEY=your_actual_api_key_here
```

Get your API key from: https://ai.google.dev/

### 3. Run the App

```bash
# For Android
flutter run

# For specific device
flutter run -d <device_id>
```

## Project Structure

```
lib/
├── main.dart                    # Entry point
├── app.dart                     # App widget & theme
├── models/
│   └── image_state.dart         # State model
├── providers/
│   └── app_provider.dart        # State management
├── services/
│   ├── gemini_service.dart      # AI integration
│   └── image_service.dart       # Image handling
├── screens/
│   └── home_screen.dart         # Main screen
└── widgets/
    ├── upload_section.dart      # Image upload UI
    ├── editor_section.dart      # Editor with preview
    ├── polaroid_frame.dart      # Polaroid styling
    └── processing_animation.dart # Loading animation
```

## Platform-Specific Setup

### Android

The `AndroidManifest.xml` already includes necessary permissions:
- Camera
- Storage (read/write)
- Internet

### iOS

The `Info.plist` already includes permission descriptions:
- Camera usage
- Photo library access
- Photo library add (saving)

## Building for Release

### Android APK

```bash
flutter build apk --release
```

### Android App Bundle (for Play Store)

```bash
flutter build appbundle --release
```

### iOS

```bash
flutter build ios --release
```

## Troubleshooting

### Common Issues

1. **API Key not found**
   - Ensure `.env` file exists in root directory
   - Verify `GEMINI_API_KEY` is set correctly
   - Run `flutter clean` and rebuild

2. **Image picker not working**
   - Check permissions in device settings
   - For iOS, ensure permissions are in `Info.plist`
   - For Android, ensure permissions are in `AndroidManifest.xml`

3. **Build errors**
   ```bash
   flutter clean
   flutter pub get
   flutter run
   ```

## Dependencies

- `google_generative_ai` - Gemini AI integration
- `image_picker` - Camera and gallery access
- `image_gallery_saver` - Save images to gallery
- `permission_handler` - Request permissions
- `provider` - State management
- `flutter_dotenv` - Environment variables
- `google_fonts` - Typography (Cormorant Garamond & Inter)

## License

Apache 2.0 - Same as the original web app
