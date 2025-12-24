# Firmware

Firmware for the smart lock MCU.

## Planned modules
- `auth/` authentication logic (hash, lockout)
- `comms/` Bluetooth/UART parsing
- `actuator/` motor/solenoid/servo control + safety timeout
- `storage/` credential storage (flash/EEPROM)

## Build (placeholder)
This repo supports multiple toolchains. Add instructions for your setup:
- STM32CubeIDE / Makefile / PlatformIO

## Safety rules (recommended)
- Always enforce actuator max-on time
- Rate limit authentication attempts
- Never print secrets in logs
