# AAE5303 Groupwork Part 1: ORB-SLAM3 VO (AMtown02)

This repository is a clean **groupwork-style Part 1 package** for Visual Odometry using ORB-SLAM3 on AMtown02.

It includes:

- VO results and leaderboard JSON
- visualizations for reporting
- reproducible configuration files
- parameter optimization notes

---

## Part 1 to Part 2 Handoff

This Part 1 repository is the upstream source for Part 2 (3DGS reconstruction):

- Part 1 output `CameraTrajectory.txt` provides camera poses
- Part 2 OpenSplat consumes those poses with images to reconstruct 3D scene

So the quality/stability of Part 1 directly determines Part 2 initialization quality.

---

## Key Results (AMtown02)

- ATE RMSE: **6.6100 m**
- RPE Trans Drift: **2.1332 m/m**
- RPE Rot Drift: **59.1839 deg/100m**
- Completeness: **98.65%**

Reference files:

- `output/PART1_AMtown02_results.md`
- `leaderboard/JinZhengzhen_leaderboard.json`

---

## Parameter Optimization and Compatibility

Main config:

- `configs/amtown_mono_groupwork.yaml`

This config keeps the validated parameter set and adds:

- `Camera.imageScale: 1.0`

Why this is added:

- Make scale choice explicit in groupwork report/tutorial format
- Keep result interpretation unchanged (`1.0` means no extra scaling factor)
- Preserve the established evaluation result path

Detailed change log:

- `docs/PARAMETER_OPTIMIZATION.md`

---

## Repository Contents

- `configs/amtown_mono_groupwork.yaml` — final VO config (with explicit `Camera.imageScale`)
- `docs/PARAMETER_OPTIMIZATION.md` — parameter history and rationale
- `figures/` — AMtown02 plots
- `leaderboard/` — submission JSON
- `output/` — result summary and evaluation JSON

---

## Visualization Assets

- `figures/amtown02_metrics.png`
- `figures/amtown02_pose_coverage.png`
- `figures/trajectory_evaluation.png`

---

## Notes

This repository focuses on **Part 1 only**.  
For full 3DGS pipeline details, use the dedicated Part 2 tutorial repository.
