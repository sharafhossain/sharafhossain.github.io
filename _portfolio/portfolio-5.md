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

Firmware for a PX4-based quadrotor at UC Berkeley. Real-time C++ on a microcontroller with limited memory and strict timing -- if the attitude loop misses a deadline, the drone falls out of the sky.

---

## What I did

Wrote the embedded C++ firmware for flight control: motor mixing, attitude stabilization, the low-level stuff. Integrated IMU and gyroscope readings for onboard state estimation.

A lot of the work was debugging. Sensor drift from vibration, communication dropouts between the flight controller and peripherals, control gains that worked on the bench but not in the air. You figure these out by staring at raw telemetry logs, not by running another simulation.

Tuned control parameters through iterative flight testing. The quad had to handle wind gusts and battery voltage drops without losing stability.

---

## Stack

C++, PX4 autopilot, embedded microcontrollers, IMU/gyroscope
