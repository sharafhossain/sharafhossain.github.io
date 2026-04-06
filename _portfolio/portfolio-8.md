---
title: "LiDAR Ray Tracing & Surface Reconstruction"
excerpt: "Time-of-flight LiDAR simulation with ray tracing and point cloud reconstruction.<br/><img src='/images/lidar-point-cloud.png'>"
collection: portfolio
category_label: deployed
priority: 3
thumbnail: "/images/lidar-raytrace.mp4"
thumbnail_type: video
status: complete
summary: "Built a full LiDAR simulation from scratch. 10,000-ray ray tracer with specular reflection off parametric surfaces, time-of-flight distance estimation, and 3D point cloud reconstruction."
highlights:
  - "10,000-ray Monte Carlo ray tracing simulation"
  - "Specular reflection with surface normal computation"
  - "Time-of-flight point cloud reconstruction"
tech:
  - Python
  - NumPy
  - SciPy
  - Ray Tracing
  - Point Clouds
  - Simulation
---

<video src="/images/lidar-raytrace.mp4" controls autoplay muted loop style="width:100%; border-radius:8px; margin-bottom:1.5em;"></video>
*10,000 rays traced from scanner to surface and back.*

![Point cloud reconstruction from LiDAR simulation](/images/lidar-point-cloud.png)
*Reconstructed surface from time-of-flight data.*

![Surface geometry](/images/lidar-surface.png)
*Ground-truth sinusoidal surface.*

## What this is

A LiDAR simulator built from scratch. 10,000 rays fire downward from a scanner at 3m height, bounce off a parametric surface via specular reflection, and return. The round-trip time gives you distance, and from that you reconstruct a 3D point cloud of whatever's below.

---

## How it works

Rays start at random (x, y) positions across a 1m x 1m domain, all pointing straight down. Forward Euler steps each ray until it hits the surface, where the surface gradient gives you the local normal and the law of reflection gives you the outgoing direction. Rays that multi-bounce or leave the domain get thrown out.

When a ray makes it back to scanner height, the total travel time plus the lateral displacement and reflection angle are enough to triangulate the surface point where it bounced. Aggregate all the returns and you get a scattered point cloud. Gridded interpolation turns that into a continuous surface.

The target surface is a 2D sinusoidal: z = 2 + A·sin(2ωπx)·sin(2ωπy), tested at A = 0.04, 0.16, and 0.64. The low-amplitude case is easy, almost everything comes back. At A = 0.64, the surface has steep enough slopes that most rays scatter out of the domain or multi-bounce, so you're reconstructing from a much sparser point cloud. Getting a clean reconstruction at that amplitude was the main challenge.

---

## Results

- Clean surface reconstruction across all three amplitudes
- At A = 0.64, ~99.8% of rays are lost to multi-bounce or domain escape, but the remaining returns are still enough for interpolation
- The failure modes are physically correct: steep slopes cause grazing-angle reflections that don't return

---

## Stack

Python, NumPy, SciPy, Matplotlib
