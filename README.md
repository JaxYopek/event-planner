# Pigeon Party App

An Android event planning and management application that allows organizers to create and manage events, entrants to join waitlists, and administrators to oversee the platform.

## Table of Contents

- [Pigeon Party App](#pigeon-party-app)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
    - [For Entrants](#for-entrants)
    - [For Organizers](#for-organizers)
    - [For Administrators](#for-administrators)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Usage](#usage)
    - [Running the App](#running-the-app)
    - [First Launch](#first-launch)
  - [Project Structure](#project-structure)
  - [Technologies Used](#technologies-used)
    - [Core Technologies](#core-technologies)
    - [Libraries \& Dependencies](#libraries--dependencies)
    - [Testing Frameworks](#testing-frameworks)
  - [Firebase Configuration](#firebase-configuration)
    - [Required Firebase Services](#required-firebase-services)
    - [Setup Steps](#setup-steps)
  - [Building the Project](#building-the-project)
    - [Debug Build](#debug-build)
    - [Release Build](#release-build)
    - [Clean Build](#clean-build)
  - [Testing](#testing)
    - [Run Unit Tests](#run-unit-tests)
    - [Run Instrumentation Tests](#run-instrumentation-tests)
    - [Run All Tests](#run-all-tests)
  - [Documentation](#documentation)
  - [Contributing](#contributing)
    - [Code Style](#code-style)
  - [License](#license)

## Features

### For Entrants
- Create and manage user profiles
- Browse available events
- Join event waitlists
- Scan QR codes to register for events
- Receive notifications about event updates
- View enrollment status

### For Organizers
- Create and manage events
- Set up facility information
- Generate QR codes for events
- Manage entrant waitlists
- Send notifications to participants
- Track event enrollment

### For Administrators
- Monitor all events and users
- Manage user accounts
- Oversee event activities
- Handle image moderation


## Prerequisites

- **Android Studio**: Latest stable version (Arctic Fox or newer recommended)
- **JDK**: Java 8 or higher
- **Android SDK**: API Level 24 (Android 7.0) or higher
- **Gradle**: 7.0 or higher (included via wrapper)
- **Firebase Account**: Required for backend services

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/JaxYopek/event-planner.git
   cd event-planner
   ```

2. **Open in Android Studio**
   - Launch Android Studio
   - Select "Open an existing project"
   - Navigate to the cloned repository folder
   - Click "OK"

3. **Configure Firebase**
   - Create a new Firebase project at [Firebase Console](https://console.firebase.google.com/)
   - Add an Android app to your Firebase project
   - Download `google-services.json`
   - Place the file in the `app/` directory (replace existing if present)

4. **Sync Gradle**
   - Android Studio should automatically sync the project
   - If not, click "File" → "Sync Project with Gradle Files"

5. **Build the project**
   ```bash
   ./gradlew build
   ```

## Usage

### Running the App

1. **Using Android Studio**
   - Connect an Android device or start an emulator
   - Click the "Run" button (green triangle) or press `Shift + F10`

2. **Using Command Line**
   ```bash
   ./gradlew installDebug
   ```

### First Launch

1. The app will request necessary permissions (notifications, camera for QR scanning)
2. Create your entrant profile
3. Browse events or switch to organizer mode to create events

## Project Structure

```
event-planner/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/pigeon_party_app/  # Source code
│   │   │   ├── res/                                 # Resources (layouts, drawables)
│   │   │   └── AndroidManifest.xml
│   │   ├── test/                                    # Unit tests
│   │   └── androidTest/                             # Instrumentation tests
│   ├── build.gradle.kts                             # App-level build configuration
│   └── google-services.json                         # Firebase configuration
├── gradle/                                           # Gradle wrapper files
├── doc/                                             # Project documentation
├── project-plan/                                     # Design documents
│   ├── crc-cards.md
│   ├── works-cited.md
│   ├── mock-ups/
│   └── story-boards/
├── build.gradle.kts                                  # Project-level build configuration
└── settings.gradle.kts                               # Gradle settings
```

## Technologies Used

### Core Technologies
- **Language**: Java 8
- **Build System**: Gradle (Kotlin DSL)
- **Minimum SDK**: API 24 (Android 7.0)
- **Target SDK**: API 34 (Android 14)

### Libraries & Dependencies
- **Firebase**: Real-time database, storage, and authentication
  - Firebase Firestore
  - Firebase Storage
  - Firebase Database
- **AndroidX**: Modern Android components
  - AppCompat
  - Material Design Components
  - ConstraintLayout
  - Activity & Fragment
- **ZXing**: QR code generation and scanning
  - `com.google.zxing:core:3.4.1`
  - `com.journeyapps:zxing-android-embedded:4.3.0`

### Testing Frameworks
- **JUnit Jupiter**: 5.0.1
- **Robolectric**: 4.8 (Android unit testing)
- **AndroidX Test**: UIAutomator for UI testing

## Firebase Configuration

### Required Firebase Services

1. **Firestore Database**
   - Collections: users, events, facilities, notifications
   
2. **Firebase Storage**
   - Used for profile pictures and event images

3. **Firebase Cloud Messaging** (Optional)
   - For push notifications

### Setup Steps

1. Enable Firestore Database in your Firebase console
2. Set up Firebase Storage
3. Configure security rules for your collections
4. Update `google-services.json` with your project credentials

## Building the Project

### Debug Build
```bash
./gradlew assembleDebug
```

### Release Build
```bash
./gradlew assembleRelease
```

### Clean Build
```bash
./gradlew clean build
```

## Testing

### Run Unit Tests
```bash
./gradlew test
```

### Run Instrumentation Tests
```bash
./gradlew connectedAndroidTest
```

### Run All Tests
```bash
./gradlew check
```

## Documentation

JavaDoc documentation is available in the following directories:
- `app/javadoc-dir/` - Initial documentation
- `app/javadocs-new/` - Updated documentation

To generate fresh JavaDocs:
```bash
./gradlew javadoc
```

Additional documentation can be found in:
- `doc/team.txt` - Team member information
- `project-plan/` - Design documents, CRC cards, and mockups

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Code Style
- Follow Java coding conventions
- Write meaningful commit messages
- Add JavaDoc comments for public methods and classes
- Include unit tests for new features

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Note**: This application requires Firebase configuration to function properly. Ensure you have set up your Firebase project and placed the `google-services.json` file in the `app/` directory before building.

For questions or issues, please open an issue on the [GitHub repository](https://github.com/JaxYopek/event-planner/issues).
