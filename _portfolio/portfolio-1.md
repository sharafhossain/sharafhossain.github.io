---
title: "Autonomous Racing: Real-Time MPC at 100 Hz"
excerpt: "Nonlinear MPC for high-speed autonomous race cars at UC Berkeley ROAR.<br/><img src='/images/av24-race.jpg'>"
collection: portfolio
featured: true
category_label: deployed
priority: 1
thumbnail: "/images/av24-race.jpg"
status: deployed
summary: "MPC controllers for the AV-24 at UC Berkeley ROAR. Tire-model-aware nonlinear optimization at 100 Hz, deployed on a real race car."
highlights:
  - "100 Hz MPC solve time (< 10ms per cycle)"
  - "150+ mph, < 15cm lateral tracking error"
  - "Full ROS 2 autonomy stack in C++ and Python"
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
*AI Racing Tech AV-24 at Las Vegas Motor Speedway.*

![Team photo with AV-24](/images/av24-ces25-team.jpeg)
*AI Racing Tech team.*

## What this is

I work on the control system for UC Berkeley ROAR's autonomous race car -- a Dallara AV-24 that races at 150+ mph with no human driver. At those speeds, with tires near saturation and 10ms between control decisions, you can't use simple PID or trajectory replay. The controller has to solve a constrained nonlinear optimization problem in real time, every cycle.

---

## The controller

The core is a nonlinear MPC built on ACADOS and CasADi. It uses a Pacejka tire model so the optimizer knows where the grip limits are, and it plans over a receding horizon with constraints on tire forces, actuator limits, track boundaries, and stability margins. Solve time stays under 10ms, which gives us 100 Hz control.

**State estimation** runs EKF/UKF fusing IMU, GPS, wheel speeds, and steering angle. It has to handle sensor dropouts gracefully -- at racing speeds, a bad estimate means you're in the wall.

**Systems integration** -- the controller sits in a ROS 2 stack alongside perception and planning. Control nodes are in C++, planning interfaces in Python. We validate in Isaac Sim before going to the real car.

---

## Numbers

- **150+ mph** autonomous driving, **< 15cm** lateral tracking error
- MPC solves in **< 10ms** consistently (100 Hz)
- Constraint satisfaction holds through aggressive cornering
- Deployed and tested in competitive autonomous racing events

---

## Stack

Python, C++, ROS 2, ACADOS, CasADi, Isaac Sim, NumPy/SciPy
