# 🌉 NyayaSetu: Clean Community App

**NyayaSetu** (Bridge to Justice) is a decentralized, offline-first, and highly accessible progressive web application (PWA) designed to empower citizens to report, track, and validate civic issues (like garbage, drainage, and road damage) in their communities. 

Built with a strong focus on **accessibility for low-literacy users**, the app features multi-language voice inputs, picture-based workflows, high-contrast modes, and a transparent escalation matrix powered by local cryptographic hashing.

---

## ✨ Key Features

### ♿ Accessibility & Low-Literacy Support
* **Visual Workflows:** Picture-based category selectors and status indicators (avoiding text-heavy dropdowns).
* **Voice Guidance & Input:** Native Text-to-Speech (TTS) instructions and Speech-to-Text (STT) complaint descriptions available in 12+ Indian languages.
* **Auto-Language Detection:** Automatically switches app and voice-input languages based on the user's GPS coordinates.
* **Simplified UI Modes:** Toggles for High-Contrast mode and Simplified View (larger text, icon-heavy).
* **Large Touch Targets:** Minimum 48px touch targets for easy navigation.

### 🚀 Core Functionality
* **Multi-Modal Authentication:** Support for Email/Password, simulated Phone OTP, and a one-click Demo Login.
* **Smart Civic Reporting:** Capture live photos via device camera, auto-fetch GPS coordinates, and optionally report anonymously.
* **Offline-First Database:** Fully functional without a backend using browser-native **IndexedDB** for storing users, sessions, complaints, and cryptographic logs.
* **Emergency Call Logs:** Dedicated flow for logging issues reported via municipal phone helplines.

### ⚖️ Transparency & Accountability
* **Tamper-Proof Logging:** Every action (creation, status update, escalation) generates a SHA-256 hash chain, ensuring complaint histories cannot be silently altered.
* **Automated Escalation Matrix:** Complaints not addressed within 72 hours are automatically escalated to higher authorities (e.g., Municipal Commissioner, District Collector).
* **NGO Verification:** Integrated workflow where local NGOs verify citizen complaints before municipal assignment to filter out spam.
* **Community Validation:** Citizens can vote (Yes/No) to verify if an issue marked as "Resolved" by authorities has actually been fixed on the ground.

---

## 🛠️ Technology Stack

NyayaSetu is built entirely using **Vanilla Web Technologies** to ensure maximum device compatibility and zero build-step overhead:

* **Frontend:** HTML5, CSS3 (CSS Variables, Flexbox, Grid), Vanilla JavaScript (ES6+).
* **Storage:** `IndexedDB` (via native API) for robust local database management.
* **Hardware APIs:** * `WebRTC` (`getUserMedia`) for live camera capture.
  * `Geolocation API` for automatic location tagging.
  * `Web Speech API` for STT (Speech Recognition) and TTS (Speech Synthesis).
* **Cryptography:** `SubtleCrypto` API for generating tamper-proof hash chains.
* **Icons:** FontAwesome 6 (CDN).

---

## 🚀 How to Run Locally

Since the application is contained entirely within a single file and uses native browser APIs, setup is instantaneous.

1. **Clone or Download the Code:**
   Save the provided code as an `.html` file (e.g., `index.html`).

2. **Serve the File:**
   *Because the app uses the Camera and Crypto APIs, it must be served over `http://localhost` or `https://` (File protocol `file://` will block camera access).*
   
   Using VS Code:
   * Install the **Live Server** extension.
   * Right-click `index.html` and select "Open with Live Server".
   
   Using Python:
   ```bash
   python -m http.server 8000
   # Then visit http://localhost:8000 in your browser
