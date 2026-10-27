# Mechatronics-Reports-MCC-ABS

**Modeling, control and simulation of mechatronic systems using MATLAB/Simulink.**

This repository contains the reports, MATLAB scripts and Simulink models produced during the **Mechatronic Systems (ES 206 / SYSMER)** course at **SeaTech — Université de Toulon**, academic year 2026-2027.

It covers two complementary projects:
1. **Electrical machine control**: direct current machine (DCM) and three-phase synchronous machine.
2. **Modeling and control of an automotive braking system**: ABS (Anti-lock Braking System) and EBD (Electronic Brakeforce Distribution).

---

## 📝 Project Overview

### 1. Motor Control — Electrical Machine Servo Systems

This report illustrates the modeling and control of mechatronic systems through the three lab sessions of the course.

- **Lab 1 — DCM model**: Electromechanical modeling (electrical and mechanical equations), open-loop simulation, identification of time constants (electrical `τe ≈ 0.69 µs` and mechanical `τm ≈ 17 ms`). Highlighting of the system stiffness and justification of the `ode15s` solver.
- **Lab 2 — Speed and position control**: Speed loop with PI controller (Kp = 2.5, Ki = 10), position loop (Kpos = 10), trapezoidal speed profile driving, current limitation and study of the impact of hardware implementation (continuous time vs. 250 Hz microcontroller vs. 50 Hz PC).
- **Lab 3 — Three-phase synchronous machine**: Modeling of the machine and inverter, scalar control (highlighting of the loss of synchronism), self-piloting (suppression of the loss of synchronism), linear analysis and influence of the angle ψ, speed control with PI (Kp = 20, Ti = 5 s).

**Files:**
- `TD1_2_3.m`: Parameter script for Labs 1, 2 and 3.
- `TD2simu.mdl`: Simulink model of the DCM servo system (speed/position).
- `TD3simu.slx`: Simulink model of the self-piloted synchronous machine.

### 2. Modeling of an ABS and EBD System

This report presents the modeling and simulation of an automotive braking system, first without and then with ABS, and the addition of the Electronic Brakeforce Distribution (EBD).

- **Braking without ABS**: Tire-road contact modeling (Coulomb model and non-linear `f(g)` curve), vehicle and wheel dynamics, braking step simulations and validation of the increased stopping distance in case of wheel lock-up.
- **Influence of the pneumatic transmission**: Addition of the low-pass filter `1/(0.01p+1)` and analysis of its impact on the braking distance.
- **Continuous-time ABS**: PID controller (Kp = 50, Ki = 20) regulating the slip around 0.2, reducing the braking distance by about 25%.
- **Discrete-time ABS**: 10 kHz sampling, behavior almost identical to the continuous case.
- **On-Off (TOR) ABS**: ±400 N steps, oscillations around the optimal slip.
- **Electronic Brakeforce Distribution (EBD)**: Consideration of load transfer (center of gravity, wheelbase), force distribution proportional to loads, verification of rear axle non-lift-off.
- **Improved ABS**: Controller optimization and analysis of the speed/stability trade-off.

**Files:**
- `ABS.m`: Parameter script for the ABS model (Kp = 50, Ki = 20).
- `ABSsimu.slx`: Simulink model of braking with ABS (continuous, discrete and TOR).
- `EBD.m`: Parameter script for the EBD model (Kp = 1, Ki = 0, vehicle geometry).
- `EBDsimu.mdl`: Simulink model of braking with EBD distributor.

---

## ✨ Key Features

* **2 complete reports** (PDF) covering all labs and the ES 206 project.
* **4 MATLAB scripts** and **4 Simulink models** ready to use.
* **Multi-physics modeling**: electrical, mechanical, thermal (via the filter), tire-road contact.
* **Control systems**: P, PI, PID, TOR controllers, in continuous and discrete time.
* **Robustness analysis**: impact of delays, sampling and saturations on stability.
