# capture lock: Modular Visual Odometry Research Platform

This repository contains a research-oriented visual odometry (VO) platform, built on top of COLMAP's geometric core, and designed to support modular substitution of key VO components. Our goal is to enable fast prototyping and benchmarking of **advanced algebraic solvers** — such as [DRaM-LHM], which is included as a case study.

Originally developed at the **Flatiron Institute**, this system is meant to provide a flexible framework for testing alternative formulations of:
- Perspective-n-Point (currently demonstrated with via DRaM-LHM in this repo)
- Essential/Fundamental matrix estimation
- Bundle adjustment
- And more

---

## Architecture




