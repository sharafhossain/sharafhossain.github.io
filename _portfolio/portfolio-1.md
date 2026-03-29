---
title: "Autonomous Racing: Real-Time MPC at 100 Hz"
excerpt: "Nonlinear MPC for high-speed autonomous race cars at UC Berkeley ROAR.<br/><img src='/images/av24-race.jpg'>"
collection: portfolio
featured: true
category_label: deployed
priority: 1
thumbnail: "/images/av24-race.jpg"
status: deployed
summary: "MPC controllers for the AV-24 at UC Berkeley ROAR. Tire-model-aware nonlinear optimization at 100 Hz, deployed on a real race car. CES 2025 winner."
highlights:
  - "100 Hz MPC solve time (< 10ms per cycle)"
  - "60+ mph, < 15cm lateral tracking error"
  - "1st place at IAC CES 2025 passing competition"
tech:
  - C++
  - Python
  - ROS 2
  - ACADOS
  - CasADi
  - Isaac Sim
  - MPC
  - EKF/UKF
---

![AV-24 at Las Vegas Motor Speedway](/images/av24-race.jpg)
*AI Racing Tech AV-24 at Las Vegas Motor Speedway. CES 2025 passing competition -- we took 1st.*

![Team photo with AV-24](/images/av24-ces25-team.jpeg)
*The team after CES 2025.*

## What this is

I work on the control system for UC Berkeley ROAR's autonomous race car -- a Dallara AV-24 that races at 60+ mph with no human driver. At those speeds, with tires near saturation and 10ms between control decisions, you can't use simple PID or trajectory replay. The controller has to solve a constrained nonlinear optimization problem in real time, every cycle.

---

## The controller

The core is a nonlinear MPC built on ACADOS and CasADi. It uses a Pacejka tire model so the optimizer knows where the grip limits are, and it plans over a receding horizon with constraints on tire forces, actuator limits, track boundaries, and stability margins. Solve time stays under 10ms, which gives us 100 Hz control.

**State estimation** runs EKF/UKF fusing IMU, GPS, wheel speeds, and steering angle. It has to handle sensor dropouts gracefully -- at racing speeds, a bad estimate means you're in the wall.

**Systems integration** -- the controller sits in a ROS 2 stack alongside perception and planning. Control nodes are in C++, planning interfaces in Python. We validate in Isaac Sim before going to the real car.

---

## Numbers

- **60+ mph** autonomous driving, **< 15cm** lateral tracking error
- MPC solves in **< 10ms** consistently (100 Hz)
- Constraint satisfaction holds through aggressive cornering
- 1st place at the Indy Autonomous Challenge passing competition, CES 2025

---

## Stack

Python, C++, ROS 2, ACADOS, CasADi, Isaac Sim, NumPy/SciPy
