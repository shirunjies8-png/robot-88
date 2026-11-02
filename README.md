# Robot 88

A compact AI desktop robot project combining embedded hardware, local voice interaction, local LLM dialogue, robot control, memory, and safety mechanisms.

> Status: Active development / Hackathon showcase repository

## Overview

Robot 88 is a small personal robot built around an ESP32-class controller and a local computer-side AI stack. The project focuses on practical human-robot interaction rather than a single demo feature.

Current capabilities include:

- Chinese voice recording and speech recognition
- Local LLM dialogue
- Text-to-speech playback
- Confirmed user memory
- Wi-Fi communication
- Web-based Robot Control Center
- Robot Control Bridge
- Motion lifecycle management
- Safety states such as BLOCKED, SAFE_STOP and E-STOP
- Planned integration of servos, distance sensing, PIR sensing, LEDs and mobile base

## System Architecture

```text
User
  |
  v
CoreS3 / ESP32
  |  Wi-Fi / Audio
  v
Voice Terminal
  |
  +--> whisper.cpp (ASR)
  |
  +--> Ollama / local LLM
  |
  +--> Memory
  |
  +--> macOS TTS
  |
  v
Robot Control Bridge
  |
  +--> Robot State Machine
  +--> Safety Checks
  +--> Hardware Adapter
  |
  v
Robot Hardware
```

## Hardware

Current / planned hardware includes:

- M5Stack CoreS3
- ESP32-series controllers
- MG90S servos
- STS3032-C001 smart servos
- N20 encoder motors
- TB6612 motor driver
- VL53L0X distance sensors
- HC-SR501 PIR sensor
- WS2812 8-LED ring
- 2S battery system
- UBEC power modules
- Hardware emergency-stop and safety power design

## Software Stack

- Node.js 22.22.2
- Python
- ESP-IDF
- whisper.cpp
- Ollama
- Local LLM
- HTTP / WebSocket
- Web Robot Control Center

## Control Bridge

Robot Control Bridge manages the command lifecycle:

```text
REQUESTED
   |
   v
VALIDATING
   |
   +--> REJECTED
   +--> BLOCKED
   |
   v
EXECUTING
   |
   +--> FAILED
   +--> TIMEOUT
   +--> SAFE_STOP
   |
   v
SUCCESS
```

The current V1 baseline has passed 23 automated tests.

## Voice Terminal

Implemented milestones:

### V1
CoreS3 recording -> Mac -> whisper.cpp -> Chinese transcription.

### V2
Local dialogue using Ollama and a local language model.

### V2.1
Confirmed memory with fields such as:

- value
- source_text
- timestamp
- confidence
- confirmed

### V3
Local TTS playback through the CoreS3 speaker.

### V4A
Wake-word integration is under development.

## Safety Design

Robot 88 treats safety as an independent system rather than an AI feature.

Planned / implemented safety concepts include:

- Hardware E-STOP
- Safety MCU
- Heartbeat monitoring
- DEGRADED state
- LOCKOUT state
- SAFE_STOP
- Obstacle blocking
- Power protection
- Command completion verification

## Repository Structure

```text
robot-88/
├── README.md
├── LICENSE
├── docs/
│   ├── architecture.md
│   ├── hardware.md
│   └── roadmap.md
├── firmware/
├── control-bridge/
├── control-center/
└── assets/
```

## Roadmap

- [x] Voice recording
- [x] Local ASR
- [x] Local LLM dialogue
- [x] Confirmed memory
- [x] Local TTS
- [x] Control Bridge V1
- [x] Web Control Center prototype
- [ ] Wake word
- [ ] Servo integration
- [ ] Mobile base integration
- [ ] Distance sensing
- [ ] Vision
- [ ] RDK board adaptation
- [ ] Full-body robot integration

## Hackathon Direction

For DDC Hackathon 2026, the next step is to migrate selected perception / interaction functions to the RDK platform while keeping the existing Robot 88 control and safety architecture.

## Author

**Shirunjie Shi**

GitHub: https://github.com/shirunjies8-png

---

This repository documents an independently developed personal robotics project and will be updated as hardware integration progresses.
