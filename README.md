# capture_lock: Modular Visual Odometry Research Platform

This repository contains a research-oriented visual odometry (VO) platform, built on top of COLMAP's geometric core, and designed to support modular substitution of key VO components. Our goal is to enable fast prototyping and benchmarking of **advanced algebraic solvers** — such as [DRaM-LHM], which is included as a case study.

Originally developed at the **Flatiron Institute**, this system is meant to provide a flexible framework for testing alternative formulations of:
- Perspective-n-Point (PnP)
- Essential/Fundamental matrix estimation
- Bundle adjustment
- And more

---

## Motivation

Most VO/SLAM pipelines treat modules like PnP or epipolar geometry as black boxes. Our goal is to open up those modules and allow **algebraically derived alternatives** — such as closed-form initializers using adjugate quaternions — to be plugged in and evaluated **under full VO pipeline conditions**.

This platform:
- Leverages COLMAP’s built-in triangulation, feature extraction, and matching
- Implements a modular factory pattern for substituting geometric components (currently demonstrated with PnP via DRaM-LHM)

---

## Architecture




