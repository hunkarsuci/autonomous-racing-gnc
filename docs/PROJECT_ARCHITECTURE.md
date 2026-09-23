# Project Architecture

## Design goal

Keep learning artifacts separate from reusable system code. The numbered folders in the repository are the knowledge map; the `racing/` package is the integrated system that grows every day.

## Active source tree

```text
racing/
├── core/        # common state/control types, conventions, units
├── dynamics/    # point mass, kinematic bicycle, dynamic bicycle
├── tires/       # tire-force models and friction limits
├── sensors/     # virtual IMU, GNSS, wheel-speed models
├── estimation/  # KF/EKF and sensor fusion
├── track/       # track data, splines, Frenet transforms
├── planning/    # racing line and velocity profiles
├── control/     # PID, Pure Pursuit, Stanley, LQR, MPC
├── simulation/  # clock, plant loop, logging, orchestration
├── validation/  # metrics, Monte Carlo, benchmark helpers
└── utils/       # shared numerical utilities
```

## Data flow

```text
truth state ──► sensors ──► estimator ──► localization ──► planner ──► controller
     ▲                                                                  │
     └──────────────────── vehicle dynamics ◄────────────────────────────┘
```

## Core interface idea

The project will converge toward a small set of explicit interfaces:

- `State`: physical state of the vehicle.
- `Control`: steering / acceleration or force commands.
- `VehicleModel.derivative(state, control)`: continuous dynamics.
- `Integrator.step(...)`: numerical propagation.
- `Sensor.measure(truth)`: noisy measurement.
- `Estimator.predict/update(...)`: estimated state and covariance.
- `Planner.plan(...)`: reference path / speed / trajectory.
- `Controller.compute(...)`: control command.
- `Simulator.step()`: orchestrates one deterministic simulation step.

The exact interfaces will be implemented incrementally rather than guessed in advance.
