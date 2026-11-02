# Hardware Inventory

This page distinguishes selected or acquired parts from fully integrated and validated subsystems.

## Main controller and interaction
| Component | Role | Status |
|---|---|---|
| M5Stack CoreS3 | Main interaction controller | Used for audio, screen, touch, and Wi-Fi experiments |
| ESP32-series boards | Embedded development | Used for firmware experiments |
| CoreS3 microphone | Voice input | Used in Voice Terminal |
| CoreS3 speaker / AW88298 path | Voice output | Used for TTS playback |

## Sensing and lighting
| Component | Role | Status |
|---|---|---|
| VL53L0X x2 | Distance sensing | Acquired; integration pending |
| HC-SR501 | Human presence sensing | Acquired; integration pending |
| WS2812 8-LED ring | Status lighting | Acquired; integration pending |

## Motion
| Component | Role | Status |
|---|---|---|
| MG90S servos | Small joint motion | Acquired; integration pending |
| STS3032-C001 | Higher-torque smart servo | Selected / acquired; integration pending |
| N20 encoder motors | Mobile base | Acquired; integration pending |
| TB6612 | DC motor control | Acquired; integration pending |

## Power and safety
- 2S battery system
- UBEC power modules
- 5 V power modules
- Fuse and power wiring components
- Low-voltage alarm and battery restraint accessories

## Integration rules
- Verify connector type, polarity, voltage, current, and signal level before each connection.
- Keep logic power and actuator power appropriately separated.
- Prefer suitable solderless connectors where practical.
- Do not infer pin assignments from connector appearance.
- Do not test physical motion until E-STOP, power protection, mechanical limits, and command timeout behavior are verified.
- Treat simulator and physical hardware test results as separate evidence.

Remove Wi-Fi credentials, API keys, tokens, serial numbers, and private network details before publishing assets.
