# Autonomous Racing Dynamics and Control

An educational and research-oriented repository for building an autonomous-racing GNC stack through vehicle dynamics, state estimation, planning, optimal control, simulation, and reproducible validation.

> **Active build track:** [60-Day Autonomous Racing GNC Build](docs/60_DAY_ROADMAP.md)  
> **System architecture:** [Project Architecture](docs/PROJECT_ARCHITECTURE.md)  
> **Daily method:** [Learning Workflow](docs/LEARNING_WORKFLOW.md)

## Two layers of the repository

This repository now has two complementary structures:

1. **The numbered modules (01–26)** are the broader knowledge map and reference curriculum.
2. **The `racing/` package + 60-day roadmap** is the active integrated engineering project.

The goal of the 60-day track is not to touch every advanced topic. It is to finish a coherent V1: dynamics + sensors + EKF + track/Frenet representation + planning + classical control + LQR + MPC + racing speed/path optimization + validation.

## Learning path / knowledge map

1. [Vehicle Dynamics Fundamentals](01_vehicle_dynamics_fundamentals/README.md)
2. [Tire Dynamics](02_tire_dynamics/README.md)
3. [Bicycle Models](03_bicycle_models/README.md)
4. [Vehicle Parameters and Load Transfer](04_vehicle_parameters_load_transfer/README.md)
5. [Vehicle Handling and Stability](05_vehicle_handling_stability/README.md)
6. [Longitudinal Vehicle Dynamics](06_longitudinal_vehicle_dynamics/README.md)
7. [State-Space Vehicle Models](07_state_space_vehicle_models/README.md)
8. [Vehicle State Estimation](08_vehicle_state_estimation/README.md)
9. [Path and Track Representation](09_path_track_representation/README.md)
10. [Path Following Control](10_path_following_control/README.md)
11. [Classical Vehicle Control](11_classical_vehicle_control/README.md)
12. [State Feedback and LQR](12_state_feedback_lqr/README.md)
13. [Optimal Control Fundamentals](13_optimal_control_fundamentals/README.md)
14. [Model Predictive Control](14_model_predictive_control/README.md)
15. [Trajectory Optimization](15_trajectory_optimization/README.md)
16. [Optimal Racing Line](16_optimal_racing_line/README.md)
17. [Planning for Autonomous Racing](17_autonomous_racing_planning/README.md)
18. [Reinforcement Learning for Racing](18_reinforcement_learning_for_racing/README.md)
19. [Optimal Control vs. RL](19_optimal_control_vs_rl/README.md)
20. [Learning-Based Vehicle Dynamics](20_learning_based_vehicle_dynamics/README.md)
21. [Robust and Adaptive Racing Control](21_robust_adaptive_racing_control/README.md)
22. [Race Simulation Architecture](22_race_simulation_architecture/README.md)
23. [Performance and Lap-Time Analysis](23_performance_lap_time_analysis/README.md)
24. [Monte Carlo and Validation](24_monte_carlo_validation/README.md)
25. [Research Experiment Design](25_research_experiment_design/README.md)
26. [Thesis Methods and Reproducibility](26_thesis_methods_reproducibility/README.md)

## Shared project structure

- `racing/`: integrated implementation built during the 60-day track.
- `docs/daily/`: one-hour daily checkpoints.
- `experiments/`: reproducible experiment entry points.
- `tracks/`: track assets and metadata.
- `shared/`: legacy/broader reusable topic-oriented utilities.
- `data/`: raw, processed, simulated, and track data.
- `configs/`: reusable system and experiment configurations.
- `tests/`: project-wide unit, integration, regression, and validation tests.
- `docs/`: theory, derivations, references, and project notes.
- `results/`: generated figures, tables, logs, and benchmarks.

## Setup

Python 3.10 or newer is recommended.

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -e ".[dev]"
pytest
```

## License

This project is available under the MIT License. See [LICENSE](LICENSE).
