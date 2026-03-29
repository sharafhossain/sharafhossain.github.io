---
layout: archive
title: "Resume"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

**Download:** [Sharaf Hossain -- Resume (PDF)](/files/Sharaf_Hossain_Resume.pdf)

---

## Summary

Robotics engineer with experience across real-time control, embedded systems, perception, and ML. I've built MPC controllers running at 100 Hz on autonomous race cars, deployed manipulation pipelines on real robot arms, and written embedded firmware for quadrotors. Also have industry experience in data engineering (HSBC) and ML (satellite infrastructure monitoring).

**Looking for full-time robotics / autonomy / ML engineering roles in the US.**

---

## Education

**University of California, Berkeley**
MEng, Mechanical Engineering -- Robotics & Control

**University College London (UCL)**
BEng, Chemical Engineering

---

## Technical Skills

| Domain | Tools & Methods |
|--------|----------------|
| **Control & Optimization** | Nonlinear MPC, ACADOS, CasADi, constrained optimization |
| **Robotics** | ROS 2, MoveIt, Isaac Sim, sim-to-real, EKF/UKF |
| **Perception** | RGB-D, YOLO, OpenCV, RealSense, LiDAR, sensor fusion |
| **ML & Simulation** | PyTorch, ML optimization, dynamics simulation, RL |
| **Software** | Python, C++, SQL, Git, ETL pipelines, embedded systems |
| **Hardware** | UR7e arms, PX4 quadrotors, Dallara AV-24 race cars |

---

## Experience

**UC Berkeley ROAR -- Autonomous AI Racing**
*Robotics & Autonomy Engineer*
- Nonlinear MPC (ACADOS/CasADi) for autonomous racing at **150+ mph, 100 Hz**
- Tire-model-aware control near the handling limits with explicit constraint satisfaction
- Full autonomy stack integration in ROS 2 and C++ across perception, planning, and control
- Team won **1st place**, IAC passing competition at CES 2025

**Warehouse Robotic Manipulation (UR7e)**
*Robotics Engineer*
- Joint-space MPC for pick-and-place with collision avoidance and actuator constraints
- Full pipeline: RGB-D detection, inverse kinematics, MPC, hardware execution
- Tested and validated on a physical UR7e in cluttered environments

**Quadrotor Embedded Systems**
*Embedded Systems Engineer*
- Wrote and deployed C++ firmware on a PX4 quadrotor for real-time flight control
- IMU and gyroscope integration for onboard state estimation
- Debugged hardware failures using raw sensor telemetry

**Letchworth Garden City Heritage Foundation** (Jul 2025 -- Aug 2025)
*Machine Learning Engineer*
- ML models for satellite-based infrastructure monitoring
- Forecasting that identified **14% energy savings** across a GBP 30M+ portfolio
- Geospatial data pipelines for large-scale datasets

**Ford Madox Ltd** -- UCL Incubated Startup (Dec 2022 -- Sep 2024)
*Co-founder*
- Led R&D for textile manufacturing, secured **GBP 30K funding**, generated **GBP 10K+ revenue**
- Delivered fire-resistant prototypes for the **UK Ministry of Defence**

**HSBC** (Jan 2024 -- Nov 2024)
*Data Engineer*
- Automated ETL pipelines processing **10,000+ unstructured datasets**, cut manual work by 40%
- Anomaly detection at **>99% compliance accuracy**
- NLP extraction models for auditable documentation

---

## Projects

See [Projects](/portfolio/) for detailed writeups:
- **Autonomous Racing** -- MPC at 100 Hz on Dallara AV-24 race cars
- **Warehouse Manipulation** -- perception + MPC pipeline on real UR7e hardware
- **Drone Swarm Sim** -- multi-agent dynamics with ML optimization
- **Quadrotor Firmware** -- PX4 embedded C++ and flight control
- **LiDAR Sim** and **Satellite Constellation Sim** -- in progress

---
