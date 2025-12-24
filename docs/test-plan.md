# Test Plan

## Firmware
- T1: Correct password unlocks
- T2: Wrong password does not unlock
- T3: Lockout triggers after N failed attempts
- T4: Actuator turns off after timeout even if MCU hangs (watchdog / fail-safe)

## Bluetooth
- T5: Connection loss during auth does not unlock
- T6: Reconnect works after disconnect

## Hardware
- T7: Driver stage survives inductive load (flyback verified)
- T8: Brownout does not leave actuator on
