# Architecture

## Core layers

1. **Interaction layer**
   - Microphone
   - Speaker
   - Touch / buttons
   - Future camera input

2. **AI layer**
   - Speech recognition
   - Local LLM
   - Memory
   - TTS

3. **Control layer**
   - HTTP / WebSocket bridge
   - Command state machine
   - Hardware adapter

4. **Safety layer**
   - E-STOP
   - Heartbeat timeout
   - Obstacle blocking
   - SAFE_STOP
   - DEGRADED / LOCKOUT

5. **Hardware layer**
   - CoreS3 / ESP32
   - Servos
   - Motors
   - Sensors
   - Lighting
