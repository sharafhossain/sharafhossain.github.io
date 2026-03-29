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

## The idea

Racing against a single clock is one problem. Racing against other cars that are also trying to win is a different, harder problem. Your optimal trajectory now depends on what the other cars do -- and they're thinking the same thing about you.

I'm extending my single-car MPC work to handle this. The approach is a hybrid: RL picks the strategy (overtake left, defend inside, wait and draft), and MPC executes it while keeping the car within its physical limits. MPC alone can't reason about strategy; RL alone can't guarantee you won't spin out at 150 mph. You need both.

**This is in progress.** The single-car MPC is done and deployed (see the racing project). Right now I'm building the multi-agent simulation environment and integrating the two layers.

---

## Architecture

```
Opponent observation → Strategic policy (MARL)
                         ↓
                    Nonlinear MPC (100 Hz)
                         ↓
                    Vehicle dynamics
```

**MPC layer** -- each car solves its own nonlinear MPC, but with predictions of where the other cars will be. Collision avoidance between vehicles shows up as coupled constraints.

**Strategy layer** -- trained with MAPPO in simulation. The policy outputs discrete decisions (overtake, defend, follow) and a reference trajectory for the MPC to track. Centralized training, decentralized execution.

**The key constraint** -- the RL policy can suggest whatever it wants, but the MPC won't execute anything that violates the dynamics. It's a safety filter. Learned policies propose, physics-aware optimization disposes.

---

## Why not just use one or the other?

- MPC by itself can't encode "wait two laps then overtake on the outside" -- that's strategic, not optimization-shaped
- RL by itself can't guarantee constraint satisfaction at 150+ mph with 10ms control loops
- The hybrid gets you both: strategic intelligence with hard safety guarantees

---

## Where it stands

- Single-agent MPC: **done**
- Multi-agent sim environment: **building now**
- Hybrid integration: **next**

---

## Stack

Python, C++, PyTorch, ACADOS, CasADi, ROS 2, Isaac Sim, MAPPO
