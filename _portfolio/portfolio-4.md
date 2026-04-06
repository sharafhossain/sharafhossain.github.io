---
title: "Multi-Agent Racing: Game-Theoretic MPC + MARL"
excerpt: "Hybrid MPC + MARL for multi-car racing."
collection: portfolio
category_label: wip
priority: 1
status: in progress
thumbnail: "/images/av24-ces25-finish.jpg"
summary: "Taking the single-car racing MPC and extending it to multi-car competition. The idea: use RL for high-level strategy (when to overtake) and MPC for low-level control (how to do it safely)."
highlights:
  - "Game-theoretic MPC with opponent prediction"
  - "RL for strategic decisions, MPC for safe execution"
  - "Single-agent components built, integration in progress"
tech:
  - Python
  - C++
  - PyTorch
  - ACADOS
  - CasADi
  - ROS 2
  - Isaac Sim
  - MAPPO
---

## The problem

Racing against a clock is one thing. Racing against other cars that are also trying to win is a fundamentally different problem. Your optimal trajectory depends on what the other cars do, and they're reasoning about you the same way. The single-car MPC I built doesn't account for any of that.

---

## The approach

Hybrid architecture: RL picks the strategy (overtake left, defend inside, wait and draft), MPC executes it within the car's physical limits.

Why not just one or the other? MPC can't encode "wait two laps then take the outside line." That's a strategic decision, not something you can express as a cost function. And RL by itself can't guarantee constraint satisfaction at 150+ mph with 10ms control loops. You need both layers.

```
Opponent observation → Strategic policy (MARL)
                         ↓
                    Nonlinear MPC (100 Hz)
                         ↓
                    Vehicle dynamics
```

Each car solves its own nonlinear MPC, but with predictions of where opponents will be. Collision avoidance between vehicles shows up as coupled constraints. The strategy layer is trained with MAPPO in simulation: centralized training, decentralized execution. Critically, the RL policy can suggest whatever it wants, but the MPC won't execute anything that violates the dynamics. It acts as a safety filter.

---

## Current status

- Single-agent MPC: **done** (see the racing project)
- Multi-agent sim environment: **building now**
- Hybrid integration: **next**

---

## Stack

Python, C++, PyTorch, ACADOS, CasADi, ROS 2, Isaac Sim, MAPPO
