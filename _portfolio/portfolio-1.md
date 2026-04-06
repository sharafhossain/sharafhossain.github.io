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

I work on the control system for UC Berkeley ROAR's autonomous race car. It's a Dallara AV-24, and at 150+ mph with tires near saturation, you get about 10ms between control decisions before the next one needs to go out. PID doesn't cut it. Trajectory replay doesn't cut it. The controller has to solve a constrained nonlinear optimization every single cycle.

---

## The controller

The core is a nonlinear MPC built on ACADOS and CasADi. It uses a Pacejka tire model so the optimizer actually knows where grip runs out, and plans over a receding horizon with constraints on tire forces, actuator limits, track boundaries, and stability margins. We keep solve time under 10ms, which gives us 100 Hz.

State estimation runs EKF/UKF fusing IMU, GPS, wheel speeds, and steering angle. The hard part isn't the filter math, it's handling sensor dropouts gracefully. At racing speeds, one bad estimate and you're in the wall.

The whole thing sits in a ROS 2 stack alongside perception and planning. Control nodes are C++, planning interfaces are Python. We validate in Isaac Sim before anything touches the real car, which has saved us more than once.

---

## What actually matters

- **150+ mph** autonomous driving, **< 15cm** lateral tracking error
- MPC solves in **< 10ms** consistently (100 Hz)
- Constraint satisfaction holds through aggressive cornering
- Deployed and tested in competitive autonomous racing events

---

## Stack

Python, C++, ROS 2, ACADOS, CasADi, Isaac Sim, NumPy/SciPy
