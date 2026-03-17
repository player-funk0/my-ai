# SmartVoiceAssistant (Kotlin)

Voice assistant MVP using:
- SpeechRecognizer (voice -> text)
- TextToSpeech (assistant replies)
- Intents (open apps, camera, settings, WhatsApp)
- CameraManager torch (flashlight on/off)
- AccessibilityService skeleton (for future automation)

## Example commands
- "open WhatsApp"
- "open YouTube"
- "open camera"
- "open settings"
- "turn on flashlight"
- "turn off flashlight"
- "send message to Ahmed saying hello"
- "send message to 0123456789 saying hello"
- "ابعت ل 0123456789 قول hello"
- "افتح الواتس و ابعت ل 0123456789 الرسالة ازيك"
- "افتح واتساب و ابعت ل Ahmed قول hello"

## WhatsApp sending note (important)
You can send to:
- A direct phone number (recommended): say the number in the command.
- A contact name (demo only): the app uses a simple in-app mapping inside `ActionExecutor.kt` (edit Ahmed's number).

## Install APK
1. Copy `app-debug.apk` to your phone.
2. Enable "Install unknown apps" for your file manager / browser.
3. Tap the APK and install.

## Permissions
- Microphone permission is required for voice input.

## Accessibility service (future automation)
To enable:
Settings -> Accessibility -> Installed services -> enable "Assistant automation service"

