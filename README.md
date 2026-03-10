# InstrumentsHelperApp

[![Java](https://img.shields.io/badge/Java-Android-red.svg)](#tech-stack)
[![Android](https://img.shields.io/badge/Android-SDK%2030-green.svg)](#prerequisites)
[![Gradle](https://img.shields.io/badge/Gradle-6.1.1-blue.svg)](#build--run)
[![Architecture](https://img.shields.io/badge/Architecture-MVP-orange.svg)](#architecture)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> **InstrumentsHelperApp** is an Android mobile application created as an engineering thesis project.  
> Its purpose is to support users in learning to play string instruments through interactive lessons, a built-in tuner, and a chord library.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Build & Run](#build--run)
- [Usage](#usage)
- [Permissions](#permissions)
- [Project Structure](#project-structure)
- [License](#license)

---

## Overview

The application was designed for Android devices to help users learn string instruments in a more interactive way than traditional tutorial-only apps.  
It combines practical exercises, instrument tuning support, lesson personalization, and a browsable chord library in a single mobile application.

The project was developed as an engineering thesis focused on supporting learning for instruments such as **guitar** and **ukulele**.

---

## Features

### Interactive learning
- Support for learning string instruments
- Lesson system divided into **difficulty levels**
- Lesson preview screen with:
  - lesson description
  - completion requirements
  - chords used in the lesson
  - user progress
  - best score

### Three lesson types
- **Playing lessons** – the user plays the displayed chord on the instrument
- **Chord lessons** – the user selects the correct chord diagram for a given chord name
- **Name lessons** – the user selects the correct chord name for a shown chord diagram

### Adaptive lesson settings
- Configurable lesson duration
- Adjustable lesson suggestion time
- Adjustable lesson frequency
- Optional adaptive lesson intensity based on user progress
- Ability to reset:
  - lesson progress
  - best scores
  - adaptive lesson intensity

### Tuner
- Built-in string instrument tuner
- Instrument selection
- Tuning selection
- Displays:
  - selected instrument
  - selected tuning
  - detected frequency
  - deviation from expected pitch
- Visual feedback when the string is correctly tuned

### Chord library
- Built-in chord book
- Chords grouped by sound/root and type
- Multiple chord variants available
- Instrument-specific chord browsing

### Additional features
- Side navigation menu for easy screen switching
- Polish and English language support based on device language
- Local data storage for app configuration and progress

---

## Architecture

The application uses the **Model–View–Presenter (MVP)** architectural pattern.

- **View** – Activities, Fragments, and UI views responsible for displaying data
- **Presenter** – handles user actions and coordinates communication between UI and logic
- **Model** – manages application data and repositories

This separation improves readability, maintainability, and modularity of the project.

---

## Tech Stack

| Area | Technology |
|---|---|
| Language | Java |
| UI | Android XML |
| Architecture | MVP |
| Database | SQLite |
| Local settings | SharedPreferences |
| Audio analysis | FFT (JTransforms) |
| UI libraries | AndroidX, Material Components |
| Build system | Gradle |
| Android plugin | Android Gradle Plugin 4.0.1 |
| Testing | JUnit, Espresso |

Main dependencies include:
- `androidx.appcompat`
- `androidx.constraintlayout`
- `androidx.legacy`
- `com.google.android.material:material`
- `com.github.wendykierp:JTransforms`

---

## Prerequisites

- **Android Studio**
- **Android SDK 30**
- **Gradle Wrapper** included in the repository
- Android device or emulator with **Android 5.1+ (API 22)**

> The project uses an older Android build configuration, so opening it in the newest Android Studio versions may require a Gradle / AGP migration.

---

## Build & Run

Clone the repository:

```bash
git clone https://github.com/Tokagero8/InstrumentsHelperApp.git
cd InstrumentsHelperApp
```

### Using Android Studio
1. Open the project in **Android Studio**
2. Wait for Gradle sync
3. Run the app on an emulator or physical device

### Using Gradle Wrapper

Build debug APK:

```bash
# Linux / macOS
./gradlew assembleDebug

# Windows
gradlew.bat assembleDebug
```

Install on a connected device:

```bash
# Linux / macOS
./gradlew installDebug

# Windows
gradlew.bat installDebug
```

---

## Usage

1. Launch the application
2. Grant required permissions
3. Choose the instrument you want to work with
4. Use one of the main sections:
   - **Tuner**
   - **Lessons**
   - **Chord Book**
5. In the lesson settings, customize:
   - lesson duration
   - preferred lesson time
   - lesson frequency
   - adaptive lesson behavior
6. Complete lessons and track your progress and best results

---

## Permissions

The application requires permissions needed for its core functionality, especially:

- **Audio recording** – required for tuner and sound-based lessons
- **Storage access** – required by the original project configuration

Without the necessary permissions, the app may not function correctly.

---

## Project Structure

```text
InstrumentsHelperApp/
├─ app/
│  ├─ src/
│  │  ├─ main/
│  │  │  ├─ java/          # Activities, fragments, presenters, models, repositories
│  │  │  ├─ res/           # Layouts, drawables, strings, icons
│  │  │  └─ AndroidManifest.xml
├─ gradle/
│  └─ wrapper/
├─ build.gradle
├─ settings.gradle
├─ gradlew
├─ gradlew.bat
└─ README.md
```

---

## License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.
