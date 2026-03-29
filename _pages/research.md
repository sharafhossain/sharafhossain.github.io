---
layout: single
title: "Research Interests"
permalink: /research/
author_profile: true
---

My research interest is in **multi-agent intelligence for physical robotic systems** -- how multiple embodied agents make decisions, coordinate, and compete in real-time under dynamics constraints and imperfect information.

This sits at the intersection of control theory, multi-agent reinforcement learning, and game theory. I'm drawn to problems where the "right" action depends not just on physics, but on what other agents will do.

---

## Core Research Questions

**1. How should optimization-based control and learned multi-agent policies share decision authority?**

MPC provides constraint satisfaction and dynamics-aware planning. MARL provides strategic reasoning about other agents. Neither is sufficient alone. The open question is how to architect their interaction: when should the learned policy override the optimizer? How do we maintain safety guarantees while allowing strategic flexibility?

*My approach*: Hierarchical architectures where MARL sets strategic objectives and MPC executes them under hard constraints. The MPC acts as a safety filter -- learned policies propose, physics-aware optimization disposes.

**2. How do agents learn to coordinate under communication constraints and partial observability?**

Real robots can't share full state. They observe each other through noisy sensors with latency. How do decentralized agents learn coordination strategies that are robust to limited, delayed, and lossy communication?

*My interest*: Emergent communication protocols in MARL, and how they compare to explicitly designed communication structures from distributed control theory.

**3. What role does game theory play in multi-agent robotic systems?**

Most MARL research treats multi-agent interaction as a black box -- throw agents into an environment and let gradient descent figure it out. Game theory provides structure: Nash equilibria, Stackelberg games, mechanism design. Can this structure improve learning efficiency and solution quality in physically grounded multi-agent problems?

*My interest*: Game-theoretic MPC formulations where agents solve coupled optimization problems, and how to scale these beyond 2-3 agents.

---

## Upcoming Research

**Vision-Language-Action Models for Humanoid Control (Summer 2026)**
Starting VLA research this summer, building on recent work in diffusion-guided whole-body humanoid control (e.g., DreamControl, ICRA 2026). The direction: using generative models trained on human motion data to produce whole-body trajectories for humanoid robots, combined with closed-loop RL for deployment. This connects generative planning with embodied control -- the same hybrid learning+optimization pattern I pursue in multi-agent settings.

---

## Specific Problem Domains

**Multi-Agent Autonomous Racing**
Multiple vehicles competing at the handling limits. Combines game-theoretic trajectory planning with real-time nonlinear MPC. Natural testbed for competitive multi-agent decision-making under dynamics constraints. [See my flagship project.](/portfolio/portfolio-4/)

**Multi-Robot Coordination**
Warehouse manipulation with multiple arms sharing a workspace. Decentralized control with shared constraints. Extends to mobile robot coordination, drone swarms, and collaborative assembly.

**Adversarial Robustness in Multi-Agent Systems**
How do learned multi-agent policies behave when one agent acts adversarially? Important for safety-critical deployment. Connects to robust control theory and adversarial RL.

---

## Technical Foundations I Build On

| Domain | Specific Areas |
|--------|---------------|
| **Control** | Nonlinear MPC, constrained optimization, game-theoretic control, distributed MPC |
| **Learning** | Multi-agent RL (MAPPO, QMIX, MADDPG), policy gradient methods, self-play |
| **Game Theory** | Nash equilibria, extensive-form games, mechanism design, fictitious play |
| **Robotics** | ROS 2, sim-to-real, state estimation, perception-to-control pipelines |
| **Software** | PyTorch, ACADOS, CasADi, C++, Python, Isaac Sim |

---

## Why This Research Direction Matters

The next generation of autonomous systems -- self-driving fleets, warehouse robot teams, aerial swarm operations -- requires agents that reason about each other, not just about physics. Current approaches either:
- Treat other agents as static obstacles (control theory)
- Ignore physical constraints entirely (most MARL)

Bridging this gap is both an engineering challenge and a research frontier. I want to build the systems and develop the theory that makes multi-agent autonomy work in the real world.

---

## Relevant Communities

- **Conferences**: CoRL, RSS, L4DC, ICRA, NeurIPS, AAMAS
- **Related labs**: Berkeley BAIR, Stanford MRL, MIT LIDS

---

*These research interests inform my engineering work. I'm also open to longer-term research opportunities in this space.*

[Email me](mailto:sharaf_hossain@berkeley.edu) | [GitHub](https://github.com/sharafhossain) | [LinkedIn](https://www.linkedin.com/in/sharafhossain)
