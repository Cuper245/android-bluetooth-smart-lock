# System Architecture

## High-level blocks
1. **Android App**
   - UI for password entry
   - Bluetooth connection to device
   - Sends authentication request and receives status

2. **MCU Firmware**
   - Receives auth request
   - Validates password (prefer hashed / challenge-response)
   - Controls actuator (unlock for N seconds)
   - Safety: timeout, retry limits, lockout after failed attempts
   - Status feedback (LED/buzzer)

3. **Actuator / Lock**
   - Solenoid, servo, or DC motor + gearbox
   - Driver stage sized for current and protection (flyback diode, fuse)

4. **Power**
   - Input (battery or adapter)
   - Regulation for MCU + actuator rail separation if needed
   - Brownout handling

## Data flow (suggested)
- Phone connects over Bluetooth
- Phone requests challenge
- MCU returns random nonce
- Phone sends response (hash(password + nonce))
- MCU compares expected hash → unlock if valid

## Interfaces
- Bluetooth: UART-to-BLE module or MCU BLE stack
- Actuator: GPIO/PWM + driver (MOSFET / H-bridge)
- Storage: internal flash or external EEPROM

## Safety & reliability
- Watchdog enabled
- Actuator max on-time (e.g., 2–5 seconds)
- Manual override button (optional)
- Debounce inputs
