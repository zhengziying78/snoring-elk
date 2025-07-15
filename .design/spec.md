# Snoring Elk — iOS App Specification

## Overview
**Snoring Elk** is a simple iOS-only app for recording and analyzing snoring during sleep.  
It is designed to be privacy-friendly, lightweight, and easy to use.

---

## Features

### 🎙 Recording
- Manual start and stop:
  - User presses **Start** before going to bed.
  - User presses **Stop** after waking up.
- Prompt user to **plug in the phone overnight** to avoid battery drain.
- **Background mode** support: 
  - Recording and snoring analysis continue even when the screen is off.
- **Automatic stop after 10 hours** (fail-safe).

---

### 📊 Data Handling
- **Saved Data:**
  1. **Audio Files**  
     - Compressed format (e.g., AAC).
     - Only **snoring segments** are saved (not continuous full-night audio).
  2. **Snoring Metadata**  
     - Time periods of detected snoring.
     - Loudness levels.
     - Other possible data points (duration, frequency, etc.).

- **User Interface:**
  - Display each night's snoring data visually.
  - Provide a **historical trend view** (e.g., week/month charts).

---

### 🔐 Privacy & Permissions
- Data is stored **locally** and in the user's **iCloud (app-private container)**.
- No data is uploaded to external servers.
- App requests **Microphone permission** explicitly and explains the usage clearly.

---

## Technical Notes

### 📱 Platform & Tech Stack
- **iOS Only**
- Written in **Swift (Native)** using **Xcode**.

---

### 🔊 Audio Analysis
- Initial Implementation:  
  - Basic heuristics (e.g., amplitude threshold, duration of sound bursts).
- Future Possibility:  
  - Offline **pre-trained ML model** embedded in the app for more accurate snore detection.
  - All processing done **locally** on the device.

---

## Out of Scope
- No Android support.
- No cloud-based storage outside of iCloud.
- No AI-based diagnosis of health conditions (sleep apnea, etc.).
- No real-time alerts or smart alarms in v1.

---

## Goals
- Simple and affordable app (single purchase, no subscription).
- High respect for user privacy.
- Reliable overnight operation.

