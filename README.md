# MyChatApp - Angular Mobile App

A demo chat application designed to showcase real-time, end-to-end encrypted messaging. Built with modern web and mobile technologies, **MyChatApp** enables secure and interactive conversations between users, serving as both a practical project and a learning resource for AngularJS, Ionic, Cordova, and Socket.IO.

---

## Table of Contents

- [Project Summary](#project-summary)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Component & File Overview](#component--file-overview)
- [API & Routing](#api--routing)
- [Installation & Setup](#installation--setup)
- [How to Run](#how-to-run)
- [Usage Guide](#usage-guide)
- [Functionality Walkthrough](#functionality-walkthrough)
- [Examples](#examples)
- [Keywords](#keywords)
- [Contributing](#contributing)
- [License](#license)
- [Screenshots](#screenshots)
- [Conclusion](#conclusion)

---

## Project Summary

**MyChatApp** is a hybrid AngularJS chat application powered by Ionic and Cordova, featuring real-time messaging, notifications, and end-to-end encryption. Designed both as a demonstration and an educational resource, it illustrates how to build modern, secure chat platforms for web and mobile.

This project is ideal for developers and students who want to learn about hybrid mobile app development, real-time communication using Socket.IO, and implementing fundamental security concepts like encryption.

---

## Features

- **End-to-End Encryption**: Private messages between users are encrypted for security.
- **Real-Time Messaging**: Send and receive messages instantly using Socket.IO.
- **User Notifications**: Get alerts when users join, leave, or are typing.
- **Cross-Platform Support**: Build as a hybrid app for Android/iOS or as a responsive web app.
- **Persistent Storage**: Stores chat history locally for offline access.
- **Responsive UI**: Clean, adaptable interface for mobile and desktop.
- **Customizable**: Easily extend with new features or integrations.

---

## Technology Stack

- **Frontend**: AngularJS, HTML5, CSS3
- **Hybrid Framework**: Ionic, Cordova
- **Real-Time Messaging**: Socket.IO
- **Storage**: JSON, Local DB storage (IndexedDB/SQLite via Cordova plugins)
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

## Component & File Overview

- **index.html**: Main entry point; loads AngularJS app, links CSS/JS.
- **js/**: JavaScript source directory.
  - **controllers.js**: Handles UI logic—joining chat, sending messages, managing notifications.
  - **services.js**: Contains services for Socket.IO communication, encryption, and storage.
  - **app.js**: AngularJS module setup, routes, and main config.
- **css/**: Application stylesheets for UI.
- **img/**: Image assets for avatars, backgrounds, and icons.
- **config.xml**: Cordova project configuration for app metadata and plugins.
- **package.json**: NPM dependencies, scripts, and project metadata.

---

## API & Routing

The client uses **Socket.IO** for all real-time events; messages are exchanged over WebSockets.

**Key Socket.IO events:**
- `'message'`: Send/receive chat messages.
- `'user joined'`: Notifies when a user joins.
- `'user left'`: Notifies when a user leaves.
- `'typing'`/`'stop typing'`: Typing notifications.

**AngularJS Routing:**
- Default route loads the chat interface.
- Login/Join screen for entering username.
- Main chat view for messaging and notifications.

*Example:*
```js
// In app.js (AngularJS)
angular.module('myChatApp', ['ionic'])
.config(function($stateProvider, $urlRouterProvider) {
  $stateProvider
    .state('login', { url: '/login', templateUrl: 'templates/login.html', controller: 'LoginCtrl' })
    .state('chat', { url: '/chat', templateUrl: 'templates/chat.html', controller: 'ChatCtrl' });
  $urlRouterProvider.otherwise('/login');
});
```

---

## Installation & Setup

### Prerequisites

- **Node.js** and **npm**
- **Ionic CLI** and **Cordova CLI**
- **Git** (to clone the repo)
- (Optional for mobile) **Android Studio** or **Xcode** for emulation

### Steps

1. **Clone the repository:**
    ```bash
    git clone https://github.com/arnobt78/MyChat--AngularApp.git
    cd MyChat--AngularApp
    ```

2. **Install dependencies:**
    ```bash
    npm install
    ```

3. **Install Ionic and Cordova globally (if not already):**
    ```bash
    npm install -g ionic cordova
    ```

4. **Add mobile platform (optional):**
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
> Opens app in default browser with live reload.

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

- **Login/Register**: Enter a username to join the chat.
- **Start Chatting**: Type messages to chat in real time with all connected users.
- **Notifications**: See when users join, leave, or are typing.
- **Encryption**: All messages are encrypted for privacy.
- **Mobile Experience**: Install the app on your device for a native-like experience.

---

## Functionality Walkthrough

### 1. User Authentication
- No password required; just pick a username to join.
- Username is stored locally for session persistence.

### 2. Real-Time Messaging
- Messages are sent/received instantly via Socket.IO.
- UI updates in real time for all users in the chat room.

### 3. Encryption
- Messages are encrypted client-side before transmission.
- Example (in service):
    ```js
    function encryptMessage(msg, key) {
      // Simple encryption (for demo)
      return btoa(msg + key);
    }
    ```

### 4. Persistent Storage
- Chat history is saved in local DB (IndexedDB/SQLite).
- On app load, chat history is restored automatically.

### 5. Notifications
- When users join, leave, or are typing, the UI shows toast or banner notifications.

### 6. Responsive UI
- Built with Ionic for adaptive layouts.
- Looks and works great on both mobile and desktop.

---

## Examples

### Example: Sending a Message

```js
$scope.sendMessage = function() {
  if ($scope.message.length) {
    var encrypted = encryptMessage($scope.message, userKey);
    socket.emit('message', { user: $scope.username, text: encrypted });
    $scope.message = '';
  }
};
```
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

## Screenshots

*Add your screenshots here to illustrate the UI and features!*

---

## Conclusion

**MyChatApp** is a practical, real-world learning project for modern hybrid app development with AngularJS and real-time technologies. Use it as a starting point for your own chat apps or as a study guide to learn about real-time messaging, encryption, and hybrid mobile frameworks.

---

## Happy Coding! 🚀

Thank you for exploring and learning with MyChatApp!  
Feel free to share, fork, and contribute!

---
