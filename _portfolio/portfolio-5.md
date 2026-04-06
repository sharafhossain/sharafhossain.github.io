---
title: "Quadrotor Embedded Systems & Flight Control"
excerpt: "Embedded C++ on a PX4 quadrotor."
collection: portfolio
category_label: deployed
priority: 3
status: deployed
summary: "Wrote and deployed C++ firmware on a PX4 quadrotor. IMU/gyro integration, attitude control, and a lot of hardware debugging."
highlights:
  - "C++ firmware on PX4 microcontroller"
  - "IMU + gyroscope fusion for attitude estimation"
  - "Debugged real flight hardware issues"
tech:
  - C++
  - PX4
  - Embedded
  - IMU
  - Real-Time Control
---

## What this is

Firmware for a PX4-based quadrotor. Real-time C++ on a microcontroller with limited memory and hard timing constraints. If the attitude loop misses a deadline, the drone falls.

---

## What I did

Wrote the motor mixing and attitude stabilization firmware. Fused IMU and gyroscope readings for onboard state estimation.

Most of the actual work was debugging, not writing new code. Sensor drift from vibration was the worst. The IMU would slowly convince the controller the drone was level when it wasn't. Communication dropouts between the flight controller and peripherals would show up randomly under load. Control gains that worked perfectly on the bench would oscillate in the air because the bench doesn't have prop wash. You diagnose these by staring at raw telemetry, not by running another simulation.

Tuned control parameters through flight testing. The quad had to handle wind gusts and battery voltage drops mid-flight without losing stability, which meant the gains couldn't be too aggressive.

---

## Stack

C++, PX4 autopilot, embedded microcontrollers, IMU/gyroscope
