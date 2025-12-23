# Real-Time Siren Detection System for Hearing Impaired Drivers

## 📌 Overview
This project implements an embedded real-time audio classification system designed to detect emergency vehicle sirens (Ambulance, Police, Fire Truck). Running on a **Raspberry Pi 5**, the system acts as a safety aid for hearing-impaired drivers by converting acoustic signals into visual alerts.

The system utilizes Google's **YAMNet** deep learning model (via TensorFlow Lite) wrapped in a custom Python environment that manages asynchronous audio buffering, sliding window processing, and temporal logic to prevent false alarms.

## 🚀 Key Features
* **Real-Time Processing:** Latency under 100ms using non-blocking I/O callbacks.
* **Custom DSP Pipeline:** Implements a sliding window algorithm (0.975s) with real-time normalization.
* **False Positive Reduction:** Includes a state machine with a 6-second cooldown timer and heuristic class aggregation.
* **Privacy Focused:** All processing is done locally on the edge (Offline); no audio is sent to the cloud.

## 🛠️ Hardware Requirements
* **Single Board Computer:** Raspberry Pi 5 (4GB or 8GB RAM recommended).
* **Input Device:** USB Microphone (Standard generic USB audio class).
* **Power Supply:** USB-C PD 27W Power Supply.

## 📂 Project Structure
```text
├── models/
│   ├── yamnet.tflite          # Pre-trained YAMNet model
│   └── yamnet_class_map.csv   # Class labels mapping
├── schematics/
│   ├── system_schematic.png   # Wiring diagram image
│   └── system_schematic.mmd   # Source file (Mermaid/Draw.io) for editing
├── src/
│   └── detect_siren.py        # Main application script
├── README.md                  # Project documentation
└── requirements.txt           # Python dependencies
