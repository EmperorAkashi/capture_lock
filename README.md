# capture lock: Modular Visual Odometry Research Platform

This repository contains a research-oriented visual odometry (VO) platform, built on top of COLMAP's geometric core, and designed to support modular substitution of key VO components. Our goal is to enable fast prototyping and benchmarking of **advanced algebraic solvers** — such as [DRaM-LHM], which is included as a case study.

Originally developed at the **Flatiron Institute**, this system is meant to provide a flexible framework for testing alternative formulations of:
- Perspective-n-Point (currently demonstrated with via DRaM-LHM in this repo)
- Essential/Fundamental matrix estimation
- Bundle adjustment
- And more

---

## Architecture
- **`workspace`** — Coordinates the VO pipeline and allows component-wise benchmarking.
- **`pnp/`** — Includes point sampling, synthetic pair generation, and scripts for PnP evaluation.
- **`estimate/`** — Contains all implemented geometric estimators. New methods can be added easily.
- **`calib_loader/`** — Provides dataset-specific calibration loading. Supports plug-and-play dataset handling.

This layout makes it easy to replace individual modules (e.g., PnP solver or feature backend) for targeted testing or integration into larger SLAM systems.

## 🚀 Getting Started

This system is designed to run inside a Docker container for reproducibility. We use the prebuilt image `cyidocker/colmap:v02`.

1. **Launch the Docker container**

   Mount your local codebase and datasets folder:
   
   `docker run -it \
     -v /your/path/to/capture_lock/:/tmp1 \
     -v /your/path/to/datasets/:/tmp3 \
     --ipc=host --shm-size=16g \
     -p 8096:8096 \
     --rm cyidocker/colmap:v02 /bin/bash`
2. **Build the project inside the container**
   `cd /tmp1/build
    make -j32`
3. **Run PnP Experiments**
   `cd /workspace/pnp
   ./pnp <data_generator_option> <method_option> <ransac_option>`








