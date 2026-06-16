# 🚀 Computer Vision Driven IoT Lighting System

> Real-Time Computer Vision Powered Smart Lighting Automation using YOLO, OpenCV, Spatial Zone Mapping, and IoT-Based Device Control.

![Python](https://img.shields.io/badge/Python-3.11-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green)
![YOLO](https://img.shields.io/badge/YOLO-Object%20Detection-orange)
![IoT](https://img.shields.io/badge/IoT-Automation-red)
![License](https://img.shields.io/badge/License-MIT-green)

---

# 📖 Overview

Traditional motion detection systems rely on PIR (Passive Infrared) sensors that suffer from:

* Blind spots
* Limited coverage
* False triggering
* Inability to identify specific occupants
* Hardware scalability challenges

This project introduces an intelligent lighting automation system powered by Computer Vision.

Using live camera feeds and real-time object detection, the system identifies human presence, maps individuals to predefined zones, and automatically controls lights based on occupancy.

---

# 🎯 Key Features

### Real-Time Person Detection

* YOLO-based object detection
* Human-only detection filtering
* Low-latency inference

### Intelligent Zone Mapping

* Define multiple lighting zones
* Resolution-independent coordinate system
* Dynamic occupancy tracking

### Automated Light Control

* Turn lights ON when a person enters a zone
* Turn lights OFF when the zone becomes empty
* Edge-triggered state management

### Multi-Zone Support

* Multiple rooms
* Hallways
* Office spaces
* Warehouses

### Performance Optimized

* Efficient detection pipeline
* Reduced computational overhead
* Scalable architecture

---

# 🏗️ System Architecture

```text
Camera Stream
      │
      ▼
Frame Capture Layer
      │
      ▼
Object Detection Engine
(YOLO)
      │
      ▼
Tracking Engine
      │
      ▼
Spatial Zone Processor
      │
      ▼
Occupancy Manager
      │
      ▼
IoT Controller
      │
      ▼
Smart Lights
```

---

# 🔄 System Workflow

### Step 1

Capture frames from:

* USB Camera
* RTSP Stream
* CCTV Camera

### Step 2

Process frames using YOLO.

Output:

```text
Person
Confidence Score
Bounding Box Coordinates
```

### Step 3

Calculate object center point.

```python
cx = (x1 + x2) / 2
cy = (y1 + y2) / 2
```

### Step 4

Check whether the person belongs to a zone.

```python
zone_xmin <= cx <= zone_xmax
zone_ymin <= cy <= zone_ymax
```

### Step 5

Update active occupancy.

### Step 6

Trigger IoT commands.

```text
Light ON
Light OFF
```

---

# 📐 Zone Detection Logic

For every detected person:

```math
ZoneActive =
(Zone_xmin ≤ Cx ≤ Zone_xmax)
AND
(Zone_ymin ≤ Cy ≤ Zone_ymax)
```

Where:

* Cx = Person center X coordinate
* Cy = Person center Y coordinate

---

# ⚡ Performance Targets

| Metric              | Target     |
| ------------------- | ---------- |
| Detection Latency   | ≤ 22ms     |
| Pipeline Latency    | ≤ 45ms     |
| Frame Rate          | 20-30 FPS  |
| Light Response Time | < 1 second |

---

# 📂 Project Structure

```text
computer-vision-iot-lighting-system/

├── docs/
│   ├── architecture/
│   ├── diagrams/
│   └── specifications/
│
├── src/
│   ├── detection/
│   ├── tracking/
│   ├── zones/
│   ├── controller/
│   └── api/
│
├── models/
│
├── configs/
│
├── deployment/
│
├── tests/
│
├── notebooks/
│
├── README.md
├── LICENSE
└── system_architecture_specification.md
```

---

# 🛠️ Technology Stack

## Computer Vision

* OpenCV
* YOLO
* NumPy

## Backend

* Python

## IoT Communication

* HTTP API
* MQTT (Future Enhancement)

## Monitoring

* Prometheus (Planned)
* Grafana (Planned)

---

# 🚀 Installation

Clone Repository

```bash
git clone https://github.com/your-username/computer-vision-iot-lighting-system.git
```

Navigate to Project

```bash
cd computer-vision-iot-lighting-system
```

Install Dependencies

```bash
pip install -r requirements.txt
```

Run Application

```bash
python main.py
```

---

# 🔐 Future Enhancements

* Multi-Camera Support
* Occupancy Heatmaps
* Face Recognition
* MQTT Integration
* Kafka Event Streaming
* Redis State Management
* Kubernetes Deployment
* Edge AI Optimization
* Smart Energy Analytics
* Mobile Dashboard

---

# 📊 Scalability Roadmap

### Current Version

* Single Camera
* Single Compute Node

### Enterprise Version

* Multi-Camera Clusters
* Distributed Event Processing
* Real-Time Analytics
* Cloud Synchronization
* Edge Device Management

---

# 📄 Documentation

Additional architecture documentation:

* System Architecture Specification
* Deployment Guide
* API Documentation
* Network Architecture

---

# 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Submit a pull request

---

# 📜 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

Aayush Dhami

Backend Engineer | System Architect | Computer Vision Enthusiast

Building scalable AI, IoT, and Microservices-based systems.
