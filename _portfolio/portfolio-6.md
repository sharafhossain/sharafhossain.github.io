---
title: "VLA Research: Diffusion-Based Humanoid Control"
excerpt: "Upcoming research on VLA models for humanoid robots."
collection: portfolio
category_label: wip
priority: 2
status: upcoming
summary: "Summer 2026 research on using diffusion models + RL for whole-body humanoid control. Building on DreamControl (ICRA 2026) for Unitree G1 deployment."
highlights:
  - "Diffusion-guided motion generation for humanoids"
  - "RL policy for sim-to-real on Unitree G1"
  - "Related to DreamControl (ICRA 2026)"
tech:
  - PyTorch
  - Diffusion Models
  - RL
  - Isaac Sim
  - Unitree G1
  - VLA
---

## What this will be

This summer I'm starting research on Vision-Language-Action models for humanoid control at UC Berkeley. The starting point is DreamControl (Kalaria et al., ICRA 2026), which trains a diffusion model on human motion data, generates whole-body trajectories, retargets them to a Unitree G1, and trains a closed-loop RL policy for deployment.

I'm currently going through the codebase and related literature to get up to speed.

---

## Direction

The general approach: use a generative model (diffusion) as a motion prior, then train task-specific RL on top of it for actual deployment. It's a similar pattern to what I'm doing with MPC + RL for racing -- a learned planner on top, a constrained executor underneath.

The new challenge is degrees of freedom. A car has a handful of control inputs. A humanoid has dozens of joints that need to coordinate for whole-body tasks.

---

## Reference

Kalaria, Harithas, Katara, Kwak, Bhagat, Sastry, Sridhar, Vemprala, Kapoor, Huang. "DreamControl: Human-Inspired Whole-Body Humanoid Control for Scene Interaction via Guided Diffusion." ICRA 2026.

---

## Stack

PyTorch, diffusion models, RL, Isaac Sim, Unitree G1
