# Flutter YOLO11n Fire & Smoke Detection (TFLite, Android)

A Flutter Android app that runs on-device YOLO11n fire and smoke detection with TensorFlow Lite, supporting both real-time camera detection and single-image inference. Includes the model conversion path from PyTorch (`.pt`) to TFLite.

## Overview

This project brings a YOLO11n fire/smoke detection model onto a mobile device, running entirely on-device via TensorFlow Lite. It demonstrates the full mobile edge-AI loop: train/obtain a model, convert it to TFLite, and integrate it into a Flutter app for live and still-image detection.

## Motivation

Fire and smoke detection is a meaningful safety use case, and doing it on-device (no cloud round-trip) is exactly the kind of edge-AI problem I want to work on. This project let me practice model conversion and mobile integration together.

## Features

- Real-time camera fire/smoke detection
- Single-image detection
- On-device inference with TensorFlow Lite
- YOLO11n model converted from `.pt` to `.tflite`
- Flutter Android application

## Architecture

```
YOLO11n (.pt)
      |
 Conversion (.pt -> .tflite)
      |
 Flutter Android App
      |
   +--+--+
   |     |
 Camera  Single Image
   |     |
   TFLite Inference
      |
 Detection Overlay
```

## Tech Stack

- **Framework:** Flutter (Dart)
- **AI/ML:** YOLO11n, TensorFlow Lite
- **Platform:** Android
- **Domain:** fire / smoke detection

## Installation

```bash
git clone https://github.com/sirVnK/Flutter-YOLO11n-Fire-Smoke-Detection-TFLite-Android-.git
cd Flutter-YOLO11n-Fire-Smoke-Detection-TFLite-Android-
flutter pub get
```

Place the converted `.tflite` model in the expected assets path (see the app config). **Large model files should not be committed to the repository** — distribute them via releases or external storage.

## Usage

```bash
flutter run
```

Grant camera permission for real-time detection, or pick a single image for still-image inference.

## Demo

> Placeholders — replace with real captures.

- `docs/demo.gif`
- `docs/screenshots/realtime-detection.png`

## Results

On-device detection runs on Android. Frame rate depends on the device; real measurements can be added here. No fabricated benchmarks are included.

## Roadmap

- [ ] Document on-device FPS on test devices
- [ ] Adjustable confidence threshold in-app
- [ ] iOS support
- [ ] Distribute model via releases (keep weights out of git)

## What I Learned

- Converting a YOLO model from PyTorch to TFLite
- Running on-device inference in Flutter
- Integrating real-time camera frames with a TFLite model
- Handling model assets and detection overlays on mobile

## Security & Privacy

No real footage, datasets, API keys or large model weights are committed. Model files are kept out of version control.

## License

MIT — see [LICENSE](LICENSE).
