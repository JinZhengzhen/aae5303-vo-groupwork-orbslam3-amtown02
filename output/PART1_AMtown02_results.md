# Part 1 Results (ORB-SLAM3, AMtown02)

This file records the current Visual Odometry baseline results for AAE5303 Part 1.

## Run Setup

- Method: ORB-SLAM3 Monocular VO
- Dataset: MARS-LVIG AMtown02
- Estimated trajectory: `CameraTrajectory.txt` (TUM format)
- Ground truth: RTK + attitude extracted to TUM format
- Evaluation protocol: Sim(3) alignment + `correct_scale`, `t_max_diff=0.1s`
- RPE delta: 10 m (distance-domain)

## Metrics

- ATE RMSE (m): `6.529045`
- RPE Trans Drift (m/m): `2.136270`
- RPE Rot Drift (deg/100m): `59.028780`
- Completeness (%): `98.706643`

## Trajectory Stats

- Estimated poses: `6715`
- Ground-truth poses: `3402`
- Matched poses: `3358`

## Notes

- Leaderboard JSON is provided at: `leaderboard/JinZhengzhen_leaderboard.json`
- This is a baseline run; further parameter tuning is planned.
