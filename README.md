# MyChatApp--AngularApp

A demo chat application designed to demonstrate real-time encrypted end-to-end messaging. Built with modern web and mobile technologies, MyChatApp enables secure and interactive conversations between users, featuring notifications, typing indicators, and more.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [How to Run](#how-to-run)
- [Usage Guide](#usage-guide)
- [Screenshots](#screenshots)
- [Keywords](#keywords)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview

**MyChatApp** is an Ionic Cordova AngularJS chat application with real-time messaging, notifications, and basic encryption. It is designed as a learning and demo project to showcase how to build a cross-platform (web and mobile) chat client using modern frameworks and best practices.

---

## Features

- **End-to-End Encryption**: Messages sent between users are encrypted to ensure privacy.
- **Real-Time Messaging**: Instant message delivery using Socket.IO.
- **User Notifications**: Get notified when users connect, disconnect, or are typing.
- **Cross-Platform Support**: Build as a hybrid mobile app or web app.
- **Persistent Storage**: Uses local DB storage for chat history.
- **Responsive UI**: Clean and simple user interface adaptable for mobile and desktop.
- **Customizable**: Easily extendable for additional features.

---

## Technology Stack

- **Frontend**: AngularJS, HTML5, CSS3
- **Hybrid Framework**: Ionic, Cordova
- **Real-Time Messaging**: Socket.IO
- **Storage**: JSON, Local DB storage (e.g., IndexedDB or SQLite via plugins)
- **Build Tools**: Node.js, NPM

---

## Project Structure

```
MyChat--AngularApp/
│
├── hooks/                 # Cordova hooks for build process customization
│   └── README.md          # Info about available hooks
│
├── platforms/             # Cordova generated platforms (android, ios, etc.)
│
├── plugins/               # Cordova/Ionic plugins
│
├── www/                   # Main application source code
│   ├── index.html         # Application entry point
│   ├── js/                # AngularJS controllers, services, app logic
│   ├── css/               # Stylesheets
│   ├── img/               # Images and assets
│   └── README.md          # Socket.IO Chat Client details
│
├── config.xml             # Cordova project configuration
├── package.json           # Project dependencies
├── README.md              # Project documentation (this file)
└── ...
```

---

## Installation & Setup

### Prerequisites

- **Node.js** and **npm**
- **Ionic CLI** and **Cordova CLI**
- **Git** (to clone the repo)
- (For mobile) **Android Studio** or **Xcode** for device emulation/build

### Steps

1. **Clone the repository:**
    ```bash
    git clone https://github.com/arnobt78/MyChat--AngularApp.git
    cd MyChat--AngularApp
    ```

2. **Install project dependencies:**
    ```bash
    npm install
    ```

3. **Install Ionic and Cordova globally (if not already):**
    ```bash
    npm install -g ionic cordova
    ```

4. **Add desired platform (optional for mobile builds):**
    ```bash
    ionic cordova platform add android
    # or
    ionic cordova platform add ios
    ```

---

## How to Run

### Run in Browser (Development)

```bash
ionic serve
```

This will open the app in your default browser with live reload.

### Run on Android/iOS Device or Emulator

```bash
ionic cordova run android
# or
ionic cordova run ios
```

### Build for Production

```bash
ionic build --prod
```

---

## Usage Guide

- **Login or Register**: Open the app and enter a username to join the chat.
- **Start Chatting**: Send messages in real-time to all connected users.
- **Notifications**: See when users join, leave, or are typing.
- **Encryption**: All messages are encrypted for privacy.
- **Mobile Experience**: Install the app on your device for a native-like experience.

---

## Screenshots

*All screenshot images from the original README are preserved below:*

---

## Keywords

Ionic, Cordova, AngularJS, HTML, CSS, JSON, DBstorage, Socket.IO, Chat, Encryption, Real-Time, Mobile, Web

---

## Contributing

Contributions are welcome! Please fork the repo and submit a pull request with your changes.

---

## License

This project is licensed under the Apache License 2.0.

---
