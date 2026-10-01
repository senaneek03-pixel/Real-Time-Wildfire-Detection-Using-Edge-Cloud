# eal-Time-Wildfire-Detection-Using-Edge-Cloud
Real-time wildfire detection system using edge computing and cloud infrastructure. A YOLOv8 model runs on an edge device to detect fire from live camera feeds and sends events to Azure IoT Hub. Azure Functions process alerts and notify users. Built with Python, OpenCV, PyTorch, and Azure cloud services.


## My Contribution — Aneek Sen ([@senaneek03-pixel](https://github.com/senaneek03-pixel))

I built the Python edge-cloud pipeline of this project:

- **Edge layer** (`edge/`): live camera capture with OpenCV, YOLOv8 inference that flags fire and smoke above a configurable confidence threshold (0.6 by default), and secure event delivery to Azure IoT Hub over TLS, with an HTTPS webhook fallback.
- **Cloud layer** (`cloud/`): an Azure Function, triggered through the IoT Hub / Event Hubs route, that sends email (SendGrid) and SMS (Twilio) alerts, plus a telemetry receiver for monitoring incoming events.
- **Deployment:** Docker packaging for the edge service, with all keys and connection strings read from environment variables.

**Tech:** Python, YOLOv8 (Ultralytics), OpenCV, PyTorch, Azure IoT Hub, Azure Functions, Azure Event Hubs, Docker
