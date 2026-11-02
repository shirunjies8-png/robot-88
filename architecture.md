# Architecture

## Core layers
1. **Interaction:** CoreS3 microphone and speaker, web interface, future touch and camera input.
2. **AI:** whisper.cpp speech recognition, Ollama local dialogue, user-confirmed memory, TTS.
3. **Communication:** Wi-Fi, HTTP APIs, WebSocket status and event channel.
4. **Control:** command validation, state machine, hardware adapter boundary.
5. **Safety:** E-STOP, heartbeat timeout, obstacle blocking, SAFE_STOP, DEGRADED / LOCKOUT concepts.
6. **Hardware:** CoreS3 / ESP32, servos, motors, sensors, status lighting.

## Voice pipeline
```text
CoreS3 microphone
  -> 16 kHz / mono / PCM16 audio capture
  -> Host computer + whisper.cpp
  -> Chinese transcription
  -> Ollama local dialogue
  -> User-confirmed memory (when approved)
  -> Host computer TTS
  -> CoreS3 speaker playback
```

## Control lifecycle
```text
REQUESTED
  -> VALIDATING -> REJECTED / BLOCKED
  -> EXECUTING -> FAILED / TIMEOUT / SAFE_STOP
  -> SUCCESS
```

The exact transitions must be checked against the implementation when source code is published.

## Safety boundary

The language model must not directly drive motors or servos. Commands must pass through a deterministic control layer and hardware-specific safety checks. Simulator validation is not a substitute for physical E-STOP tests, power-domain verification, watchdog validation, mechanical limits, and supervised low-speed testing.
