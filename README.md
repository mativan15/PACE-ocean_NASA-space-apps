# PACE learning App for NASA Space Apps

App Space Apps is a Flutter educational app prototype about NASA PACE-related ocean and ecosystem science. It introduces learners to topics such as oceans, phytoplankton, aerosols, coral reefs, and satellite-based Earth observation through a visual mobile experience with quizzes, avatar personalization, and an interactive map.

The app is designed with a student-friendly tone: large imagery, animated backgrounds, short facts, personality-style quizzes, and simple navigation between learning modules.

## Purpose

The core goal of this project is to make PACE science easier to explore through an interactive app. PACE, the Plankton, Aerosol, Cloud, ocean Ecosystem mission, observes the ocean, atmosphere, and ecosystems to help researchers understand how those systems interact.

This app translates that theme into a lightweight learning flow where users can:

- Learn introductory facts about PACE.
- Customize an avatar through a personality quiz.
- Discover their "inner plankton" result.
- Explore ocean-related learning topics.
- Read about coral reefs and answer a reef quiz question.
- View sample phytoplankton/chlorophyll markers on a Google Map.
- Navigate through placeholder areas for future arcade, streak, profile, plankton, and aerosol features.

## Current Features

### Onboarding and PACE Introduction

The onboarding flow introduces the user to the app and presents PACE as the scientific foundation for the experience. It includes:

- Welcome screen.
- PACE overview screen.
- Avatar customization entry point.

At the moment, the app launches directly into the home screen because the first-time flag in `lib/main.dart` is set to `false`.

### Home Screen

The home screen acts as the main hub. It uses an animated background and gives access to:

- Explore flow.
- User/profile page.
- Arcade placeholder.
- Streak/explore shortcut.

### Explore Flow

The explore section is built as a horizontal page experience with four topics:

- Oceans
- Plankton
- Aerosol
- Map

The Oceans and Map paths are currently implemented. Plankton and Aerosol are present as "Coming soon" sections.

### Ocean Module

The ocean module introduces ocean categories:

- Coastal Beaches
- Reefs
- Open Ocean

The Reefs path is currently active. It contains a short explanation of coral reefs and leads into a quiz screen.

### Quizzes

The app contains two quiz-style flows:

- Avatar quiz: three personality questions that lead to a plankton identity result.
- Reefs quiz: one educational question about phytoplankton and oxygen production.

These quiz screens currently support answer selection UI, but they do not yet calculate scores, validate correctness, or persist results.

### Avatar Result

After the avatar quiz, the app displays a fixed result:

`Zooxanthellae`

The result describes the user as resilient, symbiotic, connected to coral reefs, and reflective of strength, bravery, and forward thinking.

### Interactive Map

The map screen uses `google_maps_flutter` and displays sample markers in the eastern Pacific region near Peru. The markers contain phytoplankton/chlorophyll-style values intended to represent locations where plankton is present.

### Prototype Screens

Several screens are included as placeholders for future work:

- User stats/profile page.
- Arcade/game page.
- Streak-related path.
- Plankton module.
- Aerosol module.
- Chart/data visualization widget.
- Class-code dialog after the avatar result.

## Project Structure

```text
lib/
  main.dart            App entry point.
  welcome.dart         Welcome/onboarding screen.
  pace.dart            PACE introduction screen.
  home.dart            Main home hub.
  slidesss.dart        Explore page view.
  oceanos_main.dart    Ocean topic selection screen.
  reefs.dart           Reefs learning screen.
  ocea_quiz1.dart      Reefs quiz screen.
  mapa_widget.dart     Google Maps screen.
  avatar1.dart         Avatar customization entry screen.
  avatar_quiz1.dart    Avatar quiz question 1.
  avatar_quiz2.dart    Avatar quiz question 2.
  avatar_quiz3.dart    Avatar quiz question 3.
  avatar_resu.dart     Avatar result screen.
  user_page.dart       Profile/stats placeholder.
  juego.dart           Arcade/game placeholder.
  widget_graph.dart    Reusable bar chart widget prototype.

assets/
  images, GIFs, profile/avatar graphics, PACE visuals, and custom fonts.

test/
  widget_test.dart     Default Flutter test; not aligned with the current app UI.
```

The repository also contains the standard Flutter platform folders for Android, iOS, web, macOS, Linux, and Windows.

## Technology Stack

- Flutter
- Dart
- Material UI
- Google Maps Flutter
- Flutter Animate
- FL Chart
- Custom SF Pro Rounded fonts

The project also declares dependencies for local storage and formatting, such as `sqflite`, `path`, and `intl`, though those are not actively used in the current implementation.

## Assets

The app relies heavily on local visual assets under `assets/`, including:

- Background images for ocean, plankton, aerosol, map, and home screens.
- PACE and brand images.
- Avatar/profile images.
- Custom SF Pro Rounded font files.

These assets are registered in `pubspec.yaml`.

## Running the Project

Install Flutter dependencies:

```bash
flutter pub get
```

Run the app:

```bash
flutter run
```

For the Google Maps screen to work correctly on Android, the project needs a valid Google Maps API key configured in the Android manifest. If this project is shared publicly, move any real API key out of source control and restrict it in the Google Cloud Console.

## Current Limitations

This project is best understood as a prototype. Important areas still need implementation before it can be treated as a complete production app:

- The README previously used the default Flutter template and has now been replaced with this project-specific description.
- Quiz answers are not scored or validated.
- Avatar quiz answers do not affect the final result.
- User stats, streaks, class codes, and arcade gameplay are placeholders.
- Local database dependencies are declared but not used.
- Some dependencies are unused in the current source.
- The generated `build/` directory appears in the repository and should usually be ignored.
- The default widget test still checks Flutter's counter-app behavior and does not match this app.
- Several layouts use fixed sizes and may need responsive refinement for different devices.
- The app mixes English and Spanish labels in some places.

## Suggested Next Steps

- Implement real quiz scoring and feedback.
- Connect avatar quiz answers to multiple possible plankton results.
- Replace placeholder profile, streak, and arcade screens with real features.
- Add proper persistence for user progress and class codes.
- Move secrets such as map API keys out of tracked source files.
- Remove generated build artifacts from version control.
- Replace the default widget test with tests that match this app's screens.
- Add a structured navigation approach as the app grows.
