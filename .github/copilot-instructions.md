# Copilot Instructions for Mental Health Chatbot Flutter App

## Project Overview
This is a Flutter-based mobile application focused on mental health support. The app provides three main features:
- **User onboarding**: Collects and stores the user's name using `SharedPreferences`.
- **Chatbot interaction**: Simulates a simple mental health chatbot with hardcoded responses.
- **Motivational quotes**: Displays a list of motivational quotes.

## Architecture & Key Files
- All logic is currently in a single file: `app` (Dart source).
- Main components:
  - `MentalHealthApp`: Root widget, sets up theme and navigation.
  - `NameInputPage`: Handles user name input and persistence.
  - `HomePage`: Main menu, routes to chatbot and quotes.
  - `ChatBotPage`: Stateful widget for chat UI and bot logic.
  - `QuotesPage`: Stateless widget for displaying quotes.

## Data Flow & State
- User name is stored locally via `SharedPreferences` and used for personalized greetings.
- Chat messages are managed in a local list (`_messages`) within `ChatBotPage`.
- No backend or external API integration; all data is local and hardcoded.

## Developer Workflows
- **Build/Run**: Use standard Flutter commands:
  - `flutter run` to launch the app.
  - `flutter build apk` to build for Android.
- **Debugging**: Use Flutter's hot reload and debug tools.
- **Testing**: No test files present; add tests in a `test/` directory if needed.

## Project-Specific Patterns
- Navigation uses `Navigator.push` with `MaterialPageRoute`.
- State management is via `StatefulWidget` and `setState`.
- Persistent storage uses `SharedPreferences` for simple key-value data.
- Chatbot logic is hardcoded; extend `_getBotResponse` for more advanced behavior.

## Conventions
- All UI and logic are currently in a single Dart file. For larger features, split into multiple files and use clear naming (e.g., `chatbot_page.dart`, `quotes_page.dart`).
- Use Flutter best practices for widget composition and state management.

## External Dependencies
- `shared_preferences`: For local storage.
- No other third-party packages detected.

## Example Patterns
- **Saving user data:**
  ```dart
  SharedPreferences prefs = await SharedPreferences.getInstance();
  prefs.setString('userName', name);
  ```
- **Navigating between pages:**
  ```dart
  Navigator.push(
    context,
    MaterialPageRoute(builder: (context) => ChatBotPage()),
  );
  ```

## Next Steps
- For new features, follow the pattern of creating new widgets and routing via `Navigator`.
- For persistent data, use `SharedPreferences` or introduce a local database if needed.
- For more advanced chatbot logic, consider integrating with an API or using a state management solution.

---
**Feedback:** Please review and suggest any missing or unclear sections for further improvement.