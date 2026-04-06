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

Simulation of coordinated drone swarms where each agent has its own dynamics and the swarm has to avoid collisions, hold formations, and coordinate trajectories. I used ML to optimize the coordination parameters because hand-tuning them was getting nowhere. Too many interacting gains and the landscape is non-convex enough that intuition breaks down past 4-5 agents.

---

## How it works

Each drone is modeled with coupled dynamics, meaning one agent's behavior directly affects its neighbors through aerodynamic interactions and spacing constraints. The simulation handles inter-agent collision avoidance and formation objectives.

The ML optimizer learns coordination parameters (gains, waypoint timing, spacing targets) that outperform what I could set manually. The interesting part was that it generalized across swarm sizes. Parameters trained on 6 drones transferred reasonably well to 12 without retraining, though the collision margins got tighter.

The whole thing is parameterized so you can swap formation shapes, swarm sizes, and task objectives without rewriting simulation code.

---

## Results

- Collision-free trajectories across all tested configurations
- ML-optimized coordination consistently beat hand-tuned baselines, especially as swarm size grew
- The gap between hand-tuned and learned parameters got wider with more agents, which makes sense since humans are bad at reasoning about high-dimensional coupled systems

---

## Stack

Python, ML optimization, numerical simulation
