# System Architecture Specification
## Computer Vision Driven IoT Lighting System

### Executive Operational Paradigm
This system replaces traditional PIR-based automation with real-time computer vision.
The architecture separates:
- Physical Infrastructure Layer
- Cognitive Edge Layer
- IoT Control Layer

### System Architecture Deep-Dive

#### Ingestion Matrix
- RTSP / V4L2 video ingestion
- Multi-threaded frame buffering
- Queue isolation between capture and inference

#### Cognition Core Engine
- YOLO-based person detection
- Optimization by limiting detection to Person class (Class 0)
- Reduced inference overhead

#### Spatial Transformation Space
Normalized coordinate space:

R² ∈ [0.0, 1.0]

### Telemetry Flow

Bounding Box:
(x1, y1, x2, y2)

Midpoint:

Cx = (x1 + x2) / 2
Cy = (y1 + y2) / 2

Zone Activation:

ZoneActive =
(Zone_xmin ≤ Cx ≤ Zone_xmax)
AND
(Zone_ymin ≤ Cy ≤ Zone_ymax)

### Algorithmic Complexity

Runtime Complexity:

O(M × K)

Where:
- M = tracked people
- K = configured light zones

### Production Engineering

#### Network Blocking Mitigation
Replace synchronous requests.post() with:
- asyncio
- aiohttp

#### Hysteresis
Introduce:
- Frame persistence counters
- Decay thresholds
- Flicker prevention logic

#### Complex Geometry Support
Replace rectangular zones with:
- Polygon zones
- Ray-casting algorithm

### Operations Matrix

Target Performance:
- Total pipeline latency ≤ 45 ms
- Model execution ≤ 22 ms

### Recommended Production Enhancements
1. Kafka event streaming
2. Redis state cache
3. Edge AI deployment
4. Zone analytics
5. Occupancy heatmaps
6. Fault-tolerant retry mechanisms
7. Distributed monitoring and observability

---
Prepared from analysis of the uploaded computer vision IoT lighting notebook.
