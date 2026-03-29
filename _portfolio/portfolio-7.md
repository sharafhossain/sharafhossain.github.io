---
title: "Multi-Drone Swarm Simulation with ML Optimization"
excerpt: "Simulating drone swarms and using ML to optimize their coordination."
collection: portfolio
category_label: deployed
priority: 3
thumbnail: "/images/drone-swarm-sim.mp4"
thumbnail_type: video
status: complete
summary: "Simulated multi-drone swarms with coupled dynamics and used ML to optimize coordination and trajectories. Collision avoidance, formation control, scalable to different swarm sizes."
highlights:
  - "Multi-drone dynamics with collision avoidance"
  - "ML optimization beats hand-tuned baselines"
  - "Scales to different swarm sizes"
tech:
  - Python
  - ML
  - Simulation
  - Optimization
  - Multi-Agent
  - Dynamics
---

<video src="/images/drone-swarm-sim.mp4" controls autoplay muted loop style="width:100%; border-radius:8px; margin-bottom:1.5em;"></video>

## What this is

A simulation of multiple drones flying in coordinated swarms. Each drone has its own dynamics, and the swarm has to avoid collisions, maintain formations, and coordinate trajectories. I used machine learning to optimize the coordination parameters instead of hand-tuning everything.

---

## Details

**The simulation** models coupled drone dynamics -- each agent's behavior affects its neighbors. There's inter-agent collision avoidance, spacing constraints, and formation objectives.

**The ML part** optimizes swarm trajectories and coordination parameters. Instead of manually tuning gains and waypoints, the optimizer learns configurations that perform better than what I could set by hand. It generalizes across different swarm sizes.

**The infrastructure** is set up for parameterized experiments -- you can change swarm size, formation shape, task objectives and re-run.

---

## Results

- Collision-free swarm trajectories
- ML-optimized coordination outperforms hand-tuned baselines
- Works across different numbers of agents

---

## Stack

Python, ML optimization, numerical simulation
