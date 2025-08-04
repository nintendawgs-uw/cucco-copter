# Cucco-Copter Project To Do List

This file tracks all remaining work across major subsystems. Checkboxes should be updated as work is completed. Use PRs, commit messages, or contributor logs to track who handled each.

---

## Frame & Structure
- [ ] Finalize exact frame model and shape
- [ ] Choose frame material (carbon fiber, plastic, mix)
- [ ] Mount motors and verify balance/clearance
- [ ] Design component layout (MCU, battery, sensors)
- [ ] Test center of gravity

---

## Motor & Propulsion
- [ ] Estimate AUW (All-Up Weight)
- [ ] Select thrust-to-weight target (~2:1 min)
- [ ] Calculate required thrust per motor
- [ ] Choose motor and prop size
- [ ] Order parts and confirm mounting holes match frame

---

## Power System
- [ ] Budget current draw for full system
- [ ] Select ESCs rated for motors + margin
- [ ] Choose battery size (mAh), voltage (3S/4S), and connector type
- [ ] Build or buy power distribution board

---

## Flight Control
- [ ] Select MCU/dev board
- [ ] Set up toolchain and test flashing
- [ ] Integrate IMU and verify sensor readings
- [ ] Configure PWM output to ESCs
- [ ] Write or tune PID loop for hover stability

---

## Sensors & Telemetry
- [ ] Add GPS module
- [ ] Add barometer and/or magnetometer
- [ ] Add SD logging (optional)
- [ ] Set up telemetry transmission (ESP32, BLE, etc.)

---

## Communication
- [ ] Choose remote control method (RC TX/RX or phone)
- [ ] Pair controller and test failsafe
- [ ] Integrate app/ground station (optional)

---

## Optional Features
- [ ] Mount FPV or video camera
- [ ] Add video transmitter
- [ ] Evaluate follow-me or mapping logic

---

## Testing & Integration
- [ ] Power-on smoke test
- [ ] Bench test ESCs and motors
- [ ] Propeller balancing (if needed)
- [ ] First flight attempt
- [ ] Stability tuning and sensor validation

---

> Keep updating this document during planning and build stages.