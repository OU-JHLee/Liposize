# LipoSize (Inline PAT + ML) — Mac App + CLI

LipoSize is a small tool to train/compare/predict liposome-related outputs (e.g., `y1`, `y2`) using multiple ML regressors with LOOCV, and to run predictions on unseen conditions.  
This repository provides:

- ✅ **CLI binary (`liposize_tool`)**
- ✅ **Minimal Mac GUI (`LipoSize.app`)** that runs the CLI under the hood
- ✅ LOOCV evaluation (pooled RMSE) consistent with `cross_val_predict`-style scoring

---

## Features

- Feature sets:
  - **FS_A**: `x1..x7`
  - **FS_B**: `x1..x6 + x8`
  - **FS_C**: `x1..x8`
- Models:
  - LinearRegression (poly + ridge + optional target scaling)
  - Lasso (optional target scaling)
  - LinearSVR
  - PolySVR
  - XGBoost
- Commands:
  - `auto` (select best feature-set separately for y1/y2)
  - `compare` (compare feature sets)
  - `tune` (single target tuning)
  - `train` (train final model from selection json)
  - `predict` (predict for unseen data)
  - `evaluate` (evaluate on labeled data)

---

## Repository Structure

├─ main_gui.py # Tkinter GUI entry

├─ schema.json # columns definition

├─ grid.json # hyperparameter grid override

└─ dist/

└─ LipoSize.app # GUI app (PyInstaller windowed)

---

Quick Start (Mac GUI)
 - Run
   - Double-click LipoSize.app
   - Select:
     - Executable: liposize_tool (inside dist/ or the one you shipped)
     - Train CSV
     - Unseen CSV
     - schema.json
     - grid.json
     - Outdir
  - Click Run
  - The GUI will show logs in real-time.

---

## License / Usage
Copyright (c) 2026 Junghu Lee. All rights reserved.

This repository and the released binaries are provided for personal/academic evaluation only.
No permission is granted to copy, modify, redistribute, sublicense, or use for commercial purposes
without prior written permission from the author.
