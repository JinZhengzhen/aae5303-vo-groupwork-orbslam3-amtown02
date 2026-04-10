# VO Parameter Optimization Notes (AMtown02)

This document records the parameter route used for the final Part 1 VO result and explains changes for groupwork reporting.

## 1) Fixed baseline requirements

- Framework: ORB-SLAM3 monocular mode
- Dataset: AMtown02
- Output trajectory: `CameraTrajectory.txt` (TUM)
- Evaluation: Sim(3) alignment + scale correction

## 2) Effective final settings

From `configs/amtown_mono_groupwork.yaml`:

- `Camera.newWidth: 1224`
- `Camera.newHeight: 1024`
- `Camera.fps: 10` (integer for ORB-SLAM3 parser compatibility)
- `ORBextractor.nFeatures: 1500`
- `ORBextractor.iniThFAST: 18`
- `ORBextractor.minThFAST: 7`
- `Camera.imageScale: 1.0` (explicitly declared for documentation consistency)

## 3) Why add `Camera.imageScale: 1.0`

The setting is added to make scale handling explicit in configuration documentation.

- `1.0` means no extra image scaling factor beyond existing width/height settings
- This keeps the interpretation aligned with prior runs
- It is a **documentation/compatibility explicitness change**, not an intended behavior change

## 4) Metrics consistency note

The reported leaderboard metrics in this repository are kept consistent with the previously validated AMtown02 Part 1 evaluation package:

- ATE RMSE: 6.6100 m
- RPE Trans Drift: 2.1332 m/m
- RPE Rot Drift: 59.1839 deg/100m
- Completeness: 98.65%

## 5) Link to outputs

- `output/PART1_AMtown02_results.md`
- `leaderboard/JinZhengzhen_leaderboard.json`
- `output/evaluation_report.json`
