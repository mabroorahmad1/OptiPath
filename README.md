# <img src="assets/optipath_logo.png" width="40" height="40"> OptiPath: Local Network Optimization Engine

<p align="center">
  <img src="assets/thumbnail.png" width="450" height="520" alt="OptiPath Thumbnail">
</p>

Official Website & Download Link: https://optipath-release.vercel.app

OptiPath is an OS-level local network optimization engine designed to reduce ping, fix lag, and eliminate latency spikes for competitive mobile games like PUBG Mobile, Free Fire, and CODM, FPS Games.

Unlike traditional gaming VPNs that route your data through remote servers (which often increases physical latency), OptiPath acts as a smart, on-device traffic controller. It stabilizes your connection by locally shaping network bandwidth—no root access required.

## 🚀 Core Features
* **Zero-Overhead Gaming (Split Tunneling):** Leverages Android's `addDisallowedApplication()` API to explicitly exclude target games from the virtual network. Your game traffic hits the physical Wi-Fi or cellular interface directly with zero software processing delay.
* **Background Throttling (Token Bucket QoS):** Forces all non-gaming background apps into a local `tun0` virtual interface. A custom Global Token Bucket algorithm starves background updates and syncs of bandwidth, keeping the hardware queue completely empty for your game.
* **Live Network Diagnostics:** Monitor real-time ping (targeting 1.1.1.1), track Wi-Fi signal strength (-dBm), and auto-detect 2.4GHz frequency congestion to maintain peak performance.
* **Offline-First Telemetry:** Local SQLite databases cache your session duration, connection counts, and latency stability. Aggregated metrics safely sync to Firebase Firestore when the network allows.

## 📥 Download & Installation
1. Navigate to the [Releases](../../releases) page.
2. Download the latest `OptiPath-vX.X.X.apk` file from the Assets section.
3. Install the APK on your Android device (ensure "Install from Unknown Sources" is enabled).
4. Launch OptiPath, authenticate, select your target application, and launch the optimizer.

## 🛠️ Technical Architecture
* **Native Network Engine:** Kotlin, Android `VpnService`, Java NIO (Selector-based UDP proxies), thread-per-connection TCP NAT mapping.
* **Frontend UI:** Python (Flet Framework) and Flutter for high-performance, cross-platform interfaces.
* **Backend:** Firebase Authentication, Firestore (Telemetry), Realtime Database (Dynamic game package and DNS configurations), and SQLite.

## 🐛 Bug Reports & Support
OptiPath is proprietary software. The source code is closed, but this repository serves as the official distribution hub and issue tracker. 

If you encounter crashes, routing issues, or want to request support for a new mobile game, please [Open an Issue](../../issues).
---
*Note: OptiPath is proprietary software. The source code is closed, and this repository is maintained strictly for issue tracking and release distribution.*
