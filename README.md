# CameraMonitorSystem [![Build](https://github.com/concavu/CameraMonitorSystem/actions/workflows/build.yml/badge.svg?branch=main)](https://github.com/concavu/CameraMonitorSystem/actions/workflows/build.yml) ![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-lightgrey) ![Language](https://img.shields.io/badge/language-C%23-512BD4) ![License](https://img.shields.io/badge/license-MIT-blue)

<img src="assets/banner.svg" alt="CameraMonitorSystem banner" width="100%" />

> A production-ready, real-time WinForms camera streaming and AI object detection system. Built for high-performance LAN frame transmission, OpenCV image processing, and YOLO-powered human detection.

---

## 🏗️ System Architecture & Workflow

```text
[ Client (Camera Source) ] ──( LAN / TCP Streaming )──> [ Server (Receiver & AI Engine) ]
                                                                   │
                                                       ┌───────────┴───────────┐
                                                       ▼                       ▼
                                                [ OpenCV Processor ]    [ YOLO ONNX Detection ]
                                                                               │
                                                                               ▼
                                                                        [ Email Alert (SMTP) ]

```

---

## ✨ Key Features

| Feature | Description |
| --- | --- |
| **🎥 Live Streaming** | Real-time camera feed streaming across local area network nodes. |
| **⚡ Real-time Processing** | Frame processing and video manipulation powered by OpenCVSharp. |
| **📸 Event Snapshots** | Automatic capture and storage of warning snapshots upon motion/person detection. |
| **🤖 Edge AI Detection** | Optional local execution of YOLOv8 ONNX models for human detection. |
| **📧 Automated Alerts** | Direct SMTP email notifications integrated via Gmail configurations. |

---

## 🛠️ Tech Stack

* **Framework:** C# / .NET (WinForms Desktop Application)
* **Computer Vision:** OpenCVSharp & AForge.Video.DirectShow
* **AI / ML Runtime:** ONNX Runtime
* **Communication:** TCP/IP Socket networking for LAN transmission

---

## ⚡ Quick Start

### Prerequisites

* **Operating System:** Windows 10 / 11
* **SDK:** [.NET 10 SDK](https://dotnet.microsoft.com/)
* **IDE:** Visual Studio 2022 or VS Code

### 1. Restore & Build

Clone the repository and build the solution configuration:

```powershell
dotnet restore
dotnet build CameraMonitorSystem.slnx --configuration Release

```

### 2. Run the Application

Start the desktop application project:

```powershell
dotnet run --project CameraMonitorSystem.csproj

```

> 💡 *Note: Allow network access through Windows Firewall when prompted. Ensure the client streams to the correct LAN IP address and port where the server is listening.*

---

## 🤖 Optional AI Configuration

To enable YOLO-based human detection:

1. Obtain a compatible `yolov8n.onnx` model file (refer to the Ultralytics ONNX Export Guide).
2. Place the model inside the project directory before building so MSBuild copies it to output, or place it directly next to the compiled `.exe` file.
3. *The server will notify you if the model is missing, but video streaming and core features will still function normally without AI.*

---

## 🛡️ Disclaimer

This application is a prototype developed for academic networking assignments and experimental monitoring demos. It has not been designed or tested for production-grade security infrastructure.

---

## 🌐 Portfolio & Contact

Explore more of my projects and technical works at my personal portfolio:

👉 vu-tran-portfolio

```

```
