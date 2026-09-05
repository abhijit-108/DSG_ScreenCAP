# 📹 DSG ScreenCAP

<p align="center">
  <img src="https://raw.githubusercontent.com/abhijit-108/DSG_ScreenCAP/main/app_logo.png" alt="DSG ScreenCAP Logo" width="120" height="120" />
</p>

<p align="center">
  <strong>A modern, high-performance screen recording and capture studio for Android built with Jetpack Compose & Hardware-Accelerated MediaCodec.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Version-v4.0.3-9D4EDD?style=for-the-badge" alt="Version" />
  <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Platform" />
  <img src="https://img.shields.io/badge/Kotlin-2.3.20-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white" alt="Kotlin" />
  <img src="https://img.shields.io/badge/Compose-BOM_2026.03-4285F4?style=for-the-badge&logo=jetpackcompose&logoColor=white" alt="Compose" />
  <img src="https://img.shields.io/badge/Target_SDK-API_36-FF6F00?style=for-the-badge&logo=android&logoColor=white" alt="Target SDK" />
</p>

---

## 🌟 Overview

**DSG ScreenCAP** is an advanced, hardware-accelerated screen capture and recording utility engineered for Android. Combining a pure OLED dark theme with vibrant neon purple accents, DSG ScreenCAP delivers lag-free recording up to **120 FPS**, bitrates up to **50 Mbps**, internal system audio capture, dynamic floating overlay controls, and a suite of dedicated **Quick Settings Tiles** for instant zero-launch recording.

---

## ✨ Features

### ⚡ Hardware-Accelerated Capture Engine
- **High Frame Rates**: Record silky-smooth footage at **60 FPS**, **90 FPS**, or **120 FPS** for fast-paced gaming and high-refresh-rate displays.
- **Multi-Codec Encoding**: Leverages hardware encoding via `MediaCodec` with support for **H.264 (AVC)** (maximum device compatibility), **H.265 (HEVC)** (efficient file compression), and **AV1 (Next-Gen)**.
- **Flexible Resolutions**: Capture at **Original** (native screen resolution), **1080p Full HD**, or **720p HD**, with intelligent aspect ratio preservation and hardware-aligned dimensions.
- **Granular Bitrate Control**: Choose between dynamic **Adaptive Bitrate** (auto-calculated from resolution and frame rate) or precision presets: **9 Mbps**, **15 Mbps**, **20 Mbps**, **30 Mbps**, **40 Mbps**, and **50 Mbps**.
- **Orientation Lock**: Set capture orientation to **Auto**, locked **Portrait**, or locked **Landscape**.
- **5-Second Countdown Timer**: Smart visual buffer and notification countdown to prepare your screen before recording begins.

### 🎯 Quick Settings Tile Ecosystem
Transform your Android Quick Settings panel into a 1-tap capture station without ever opening the app:
- **`DSG_Rec`**: Instant capture using your custom configured settings.
- **`DSG_iqoo13`**: High-performance flagship preset (**Original Resolution • 60 FPS • 30 Mbps**).
- **`DSG_pad7`**: High-bitrate tablet preset (**Original Resolution • 60 FPS • 40 Mbps**).
- **`DSG_Priya`**: Balanced high-efficiency preset (**1080p • 60 FPS • 15 Mbps**).
- **`DSG_Lowest`**: Ultra storage-saver preset (**1080p • 60 FPS • 9 Mbps**).
- **Live Tile State**: Real-time tile status toggles to active while recording; tap anytime to immediately stop.

### 🎛️ Floating Overlay & Notification Controls
- **Draggable Floating Controller**: Interactive Compose bubble with real-time elapsed recording timer, pause/resume, stop, and sound toggle.
- **Adjustable Opacity**: Customize controller opacity from **10%** to **100%** via an integrated slider in Settings.
- **Custom Notification Controller**: Foreground service notification featuring custom `RemoteViews` with inline **Pause**, **Resume**, **Stop**, and **Sound Toggle** buttons.

### 🔊 High-Fidelity Internal Audio Recording
- **Internal System Audio**: Direct digital sound capture via Android's `AudioPlaybackCaptureConfiguration` for gameplay, tutorials, and music with zero microphone feedback or ambient room noise.
- **Stereo AAC Output**: 48 kHz sampling rate with pristine 192 kbps stereo AAC encoding.
- **On-the-Fly Sound Toggle**: Instantly mute or unmute audio capture mid-recording via the floating bubble or notification bar.

### 📂 Integrated Media Manager
- **Organized Storage**: Recordings automatically save to `Movies/DSG Records/` for clean gallery organization.
- **Sequential Naming**: Conflict-free auto-incrementing naming scheme (`recording_1.mp4`, `recording_2.mp4`).
- **In-App Library**: Browse recorded videos with real-time metadata including video duration, file size, and creation date.
- **Quick Actions**: 1-tap playback via your default media player (e.g. *DSG PlayIT*), 1-tap social sharing via Android Sharesheet, and instant file deletion with MediaStore synchronization.

### 🔄 In-App Automatic Updater
- **Direct GitHub Releases Sync**: Check for new updates directly within Settings.
- **In-App APK Download & Install**: Stream updates from GitHub with an animated progress modal and automatic package installer prompt.

---

## 🛠️ Tech Stack & Architecture

- **Language**: Kotlin 2.3.20
- **UI Framework**: Jetpack Compose (Material 3, Material Icons)
- **Architecture**: Modern Android MVVM + Kotlin Coroutines + StateFlow
- **Navigation**: AndroidX Navigation 3 (`navigation3-ui`, `navigation3-runtime`)
- **Screen Capture Engine**: Android MediaProjection API + Asynchronous `MediaCodec` + `MediaMuxer`
- **Audio Capture**: `AudioPlaybackCaptureConfiguration` + `AudioRecord` (16-bit PCM, 48 kHz)
- **Data Persistence**: AndroidX DataStore Preferences 1.1.1
- **Target OS**: Android 7.0 (API 24) through Android 16 (API 36, targetSdk 36)

---

## 📥 Download & Installation

1. Navigate to the **[Releases](https://github.com/abhijit-108/DSG_ScreenCAP/releases)** tab on GitHub.
2. Download the latest **`app-debug.apk`**.
3. Open the downloaded `.apk` file on your Android device.
4. When prompted, enable **"Install from unknown sources"** in your system settings.
5. Launch **DSG ScreenCAP** and grant the required recording and overlay permissions to begin capturing.

---

## 🔒 Permissions

DSG ScreenCAP requests the following permissions to provide high-performance screen recording and floating control capabilities:

| Permission | Purpose |
| :--- | :--- |
| `FOREGROUND_SERVICE` | Keeps the capture service running reliably in the background |
| `FOREGROUND_SERVICE_MEDIA_PROJECTION` | Captures screen frames via Android MediaProjection |
| `RECORD_AUDIO` | Records internal system audio and microphone sound |
| `SYSTEM_ALERT_WINDOW` | Displays the draggable floating recording controller and timer |
| `POST_NOTIFICATIONS` | Shows real-time recording status and inline controls in the notification drawer |
| `INTERNET` | Checks for app updates and downloads newer APK releases from GitHub |
| `REQUEST_INSTALL_PACKAGES` | Prompts installation of downloaded in-app updates |

---

## 📋 Changelog

### `v 4.0.3`
- **Tile Ecosystem Expansion**: Added dedicated Quick Settings tiles for `DSG_iqoo13`, `DSG_pad7`, `DSG_Priya`, `DSG_Lowest`, and `DSG_Rec`.
- **High Frame Rate Support**: Added 90 FPS and 120 FPS high-refresh-rate recording profiles.
- **Adaptive Bitrate Algorithm**: Added intelligent dynamic bitrate estimation based on resolution and framerate.
- **Hardware Encoder Stability**: Added asynchronous `HandlerThread` for `MediaCodec` to eliminate dropped frames.

### `v 4.0.2`
- **Floating Overlay Controller**: Integrated draggable Compose widget with magnetic snapping and customizable opacity slider.
- **In-App GitHub Updater**: Added automatic update checker and APK download manager in Settings.
- **Android 16 Support**: Updated target SDK to Android 16 (API 36) with AndroidX Navigation 3.

### `v 4.0.0`
- **OLED Neon Theme**: Complete redesign with pure black surfaces and neon purple accents.
- **Folder Scoped Storage**: Standardized storage path to `Movies/DSG Records` with sequential file naming.
- **Internal Audio Playback**: Implemented zero-noise `AudioPlaybackCapture` pipeline.

### `v 1.0.0`
- **Initial Release**: Core MediaProjection recording engine with MediaMuxer integration.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
