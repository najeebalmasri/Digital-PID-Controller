# 🔧 Digital PID Controller — ELE709 Real-Time Computer Control Systems

This project involves the design and implementation of digital PID controllers (Basic and Anti-Windup) for controlling the position of a DC motor. It uses concurrent programming with **Pthreads** and integrates both **simulation** and **real hardware** testing using the **DLaB Library**.

---

## 📌 Project Objectives

### ✅ Part A: Simulation
- Design PID controller using **Ultimate Sensitivity Method**
- Implement and simulate Proportional and PID controllers
- Use `Pthreads` for real-time concurrent programming
- Test with step and square wave inputs
- Visualize outputs using plotting functions

### ✅ Part B: Hardware Testing
- Run controller on actual DC motor hardware via micro-controller board
- Test performance under various input signals
- Evaluate control response with **loading conditions**

### ✅ Part C: Further Extension
- Implement continuous run mode with interactive parameter adjustment
- Store and visualize last 3 seconds of output on request

---

## 💻 Technologies & Tools

- **C Programming**
- **Pthreads**
- **POSIX semaphores**
- **DLaB Hardware Library**
- **Simulation Mode (`simcc`)**
- **Hardware Mode (`hwcc`)**

---

## 📁 File Structure

- `pc.c` – Proportional controller implementation
- `pid.c` – Basic PID controller code
- `antiwindup_pid.c` – Anti-windup PID controller code
- `dlab_def.h` – Required header for DLaB functions
- `newload.c` – Loading simulation script

---

## 🧠 Key DLaB Functions Used

| Function         | Purpose                                                  |
|------------------|----------------------------------------------------------|
| `Initialize()`   | Setup sampling frequency and mode                        |
| `Terminate()`    | Shutdown hardware communication                          |
| `ReadEncoder()`  | Get encoder pulse count                                  |
| `EtoR()`         | Convert encoder value to radians                         |
| `DtoA()`         | Send digital control value to D/A converter              |
| `VtoD()`         | Convert voltage to digital code                          |
| `plot()`         | Plot and optionally save results                         |
| `Square()`       | Generate square wave input                               |

---

## 📊 Control System Overview

The system uses two `Pthreads`:
- `main()` handles interface and setup
- `Control()` handles real-time PID computation

A high-level overview of interaction with micro-controller:
