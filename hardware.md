# Hardware

## Confirmed / available components

| Module | Purpose |
|---|---|
| M5Stack CoreS3 | Main interaction controller |
| MG90S servos | Small joints / motion |
| STS3032-C001 | Higher torque smart servo |
| N20 encoder motors | Mobile base |
| TB6612 | Motor driver |
| VL53L0X | Distance sensing |
| HC-SR501 | Human presence sensing |
| WS2812 8-LED ring | Status / expression |
| UBEC modules | Power conversion |
| 2S battery | Robot power source |

## Design principles

- Prefer solderless wiring where practical
- Separate logic and actuator power domains
- Use explicit safety states
- Do not allow AI output to bypass hardware safety checks
