# 60-Day Autonomous Racing GNC Build

This is the active execution path for the repository. The older numbered modules remain as the broader knowledge map; this plan turns that map into one integrated, testable autonomous-racing system.

## Operating rule

- **1 day = 1 focused 60-minute session.**
- A topic may span multiple days; mastery matters more than calendar speed.
- Every session must end with an observable artifact: code, test, plot, derivation check, benchmark, or integration result.
- Copy/paste is allowed for speed; unexplained copy/paste is not. Important lines must be understood physically, mathematically, and programmatically.
- The project is simulation-first and Python-first for rapid learning. Production-style structure, testing, interfaces, and selected C++ concepts are introduced when they materially help the engineering goal.

## Default 60-minute session

| Time | Activity |
|---|---|
| 0–10 min | Physical intuition and engineering context |
| 10–25 min | Mathematics and derivation |
| 25–50 min | Implementation / experiment |
| 50–60 min | Validation + 3–5 oral review questions |

## Phases

| Days | Phase | Outcome |
|---|---|---|
| 1–7 | Foundations & simulation | State-space thinking, frames, integration, first simulator |
| 8–14 | Kinematic vehicle model | Steering geometry, bicycle model, numerical validation |
| 15–25 | Vehicle & tire dynamics | Newton–Euler, slip, tire forces, dynamic bicycle, handling |
| 26–36 | State estimation | Sensors, probability, KF/EKF, fusion, validation |
| 37–45 | Track & classical control | Splines, Frenet, Pure Pursuit, Stanley, PID, benchmarking |
| 46–50 | State-space & LQR | Linearization, controllability, LQR design/tuning |
| 51–57 | Optimization & racing | MPC, racing line, velocity planning |
| 58–60 | Integration & validation | Full stack, robustness, final benchmark |

## Daily plan

| Day | Focus | Core learning | End-of-day evidence |
|---:|---|---|---|
| 1 | System Architecture & Project Contract | GNC loop, state/input/output, repository roles | Architecture diagram + agreed state/input notation |
| 2 | Coordinate Frames | Global/body frames, vectors, rotation matrix | Frame transform helper + sanity checks |
| 3 | Vehicle State & Units | State vectors, control vectors, SI units, conventions | Typed state/control data model |
| 4 | Continuous-Time Dynamics | Derivatives, ODEs, xdot=f(x,u) | First derivative function |
| 5 | Discretization & Time Step | Euler integration, dt, numerical error | Discrete propagation function |
| 6 | Point-Mass 2D Simulation | Position/velocity propagation | First moving vehicle simulation |
| 7 | Validation & Week-1 Review | Physical sanity checks, plotting, invariants | Validated baseline + review questions |
| 8 | Steering Geometry | Ackermann intuition, wheelbase, curvature | Steering/turn-radius visual check |
| 9 | Kinematic Bicycle Derivation | Geometry behind yaw rate and pose dynamics | Derivation note + equations |
| 10 | Kinematic Bicycle Implementation | Nonlinear kinematic model | Working kinematic bicycle simulator |
| 11 | Euler vs RK4 | Numerical integration accuracy/stability | Integrator comparison experiment |
| 12 | Simulation Logging | Time histories, state/control logging | Reusable logger + plots |
| 13 | Parameters & Configuration | Vehicle parameters, dataclasses/config files | Central vehicle config |
| 14 | Model Unit Tests | Test design for numerical models | Kinematic model unit tests |
| 15 | Newton-Euler Foundations | Force/moment balance, rigid-body dynamics | Vehicle free-body model notes |
| 16 | Longitudinal Dynamics | Drive/brake forces, drag, rolling resistance | Longitudinal acceleration model |
| 17 | Lateral & Yaw Dynamics | Lateral force balance and yaw moment | Lateral/yaw equations |
| 18 | Slip-Angle Geometry | Velocity at axles, alpha_f/alpha_r | Slip-angle implementation |
| 19 | Linear Tire Model | Cornering stiffness and Fy=-Cα | Linear tire-force model |
| 20 | Dynamic Bicycle I | Choose states and derive lateral dynamics | State equations part 1 |
| 21 | Dynamic Bicycle II | Coupled vy/r and global pose dynamics | Complete derivation |
| 22 | Dynamic Bicycle Implementation | ODE implementation and simulation | Working dynamic bicycle model |
| 23 | Friction Circle | Combined longitudinal/lateral grip limit | Grip-limit checks + plot |
| 24 | Handling Balance | Understeer/oversteer and parameter effects | Handling parameter study |
| 25 | Dynamic-Model Validation | Steady-state cornering and consistency | Validated dynamic-model baseline |
| 26 | Sensor Models | Measurement equation z=h(x)+v | Sensor interface + measurement models |
| 27 | IMU/GNSS/Wheel Speed | Noise, bias, dropout, sampling rates | Virtual sensor suite |
| 28 | Probability & Covariance | Gaussian noise, covariance, uncertainty | Noise/covariance experiment |
| 29 | 1D Kalman Filter | Predict/update intuition | Working scalar KF |
| 30 | Multidimensional KF | Matrix KF and covariance propagation | Linear state estimator |
| 31 | EKF Linearization | Jacobians F/H and nonlinear models | Analytic/numeric Jacobian checks |
| 32 | EKF Prediction | Nonlinear propagation + covariance | EKF predict step |
| 33 | EKF Measurement Updates | GNSS/IMU/wheel measurement updates | EKF update step |
| 34 | Sensor Fusion Integration | Asynchronous measurements and full estimator | Integrated EKF localization |
| 35 | Estimator Tuning | Q/R tuning, innovation/residuals | Tuning experiment + plots |
| 36 | Estimator Validation | RMSE, bias, consistency checks | Estimator validation report |
| 37 | Track Representation | Waypoints, boundaries, centerline | Track data structure |
| 38 | Splines & Arc Length | Smooth interpolation and s-coordinate | Spline centerline |
| 39 | Curvature | κ(s), geometric meaning and computation | Track curvature profile |
| 40 | Frenet Coordinates | s, e_y, e_psi and transforms | Cartesian↔Frenet utilities |
| 41 | Tracking Errors | Nearest point, cross-track/heading errors | Reusable error computation |
| 42 | Pure Pursuit | Look-ahead geometry | Pure-pursuit autonomous lap |
| 43 | Stanley Control | Heading + cross-track feedback | Stanley autonomous lap |
| 44 | Longitudinal PID | Speed feedback and actuator limits | Speed controller |
| 45 | Controller Benchmark | Metrics, tracking error, steering effort | PP vs Stanley vs PID results |
| 46 | State-Space Linearization | A/B matrices around operating point | Linearized vehicle model |
| 47 | Controllability & Discretization | Controllability matrix, Ad/Bd | Controllability checks |
| 48 | LQR Derivation | Quadratic cost and Riccati intuition | LQR formulation note |
| 49 | LQR Implementation | State feedback for lateral tracking | Working LQR controller |
| 50 | LQR Tuning | Q/R trade-offs and speed dependence | LQR benchmark + tuning plots |
| 51 | Optimization Fundamentals | Decision variables, objective, constraints | Small optimization sandbox |
| 52 | MPC Prediction Model | Horizon and stacked dynamics | Prediction matrices/model |
| 53 | MPC Cost Function | Tracking, effort, rate penalties | Cost implementation |
| 54 | MPC Constraints | Steering, rate, acceleration, track limits | Constrained MPC problem |
| 55 | MPC Implementation | Receding-horizon solve and control loop | Working MPC lap |
| 56 | Racing-Line Optimization | Track boundaries and minimum-curvature intuition | Baseline optimized racing path |
| 57 | Velocity Planning | Curvature/grip speed limit + forward/backward pass | Feasible racing speed profile |
| 58 | Full-Stack Integration | EKF → track/Frenet → planner → controller → vehicle | End-to-end autonomous lap |
| 59 | Robustness & Monte Carlo | Noise, delay, model mismatch, parameter spread | Monte Carlo robustness results |
| 60 | Final Benchmark & Release | Lap time, RMSE, plots, failure cases, documentation | Autonomous Racing Car v1.0 report/demo |

## Definition of done for V1

The 60-day V1 is complete when the repository contains an end-to-end simulation with:

1. kinematic and dynamic bicycle models,
2. basic tire-force limits,
3. noisy virtual sensors,
4. EKF-based state estimation,
5. track spline + Frenet representation,
6. classical tracking baselines,
7. LQR and constrained MPC,
8. racing-path / velocity planning,
9. reproducible benchmarks,
10. robustness tests under noise, delay, and model mismatch.

The final system should support this loop:

```text
Sensors
   ↓
State Estimator (EKF)
   ↓
Track / Frenet Localization
   ↓
Path + Velocity Planning
   ↓
Controller (baseline / LQR / MPC)
   ↓
Vehicle + Tire Dynamics
   ↓
Sensors
```

## Phase 2 (after Day 60)

Not required for V1: nonlinear tire models/Pacejka, load-transfer refinement, aero/downforce, nonlinear MPC, minimum-time direct optimal control, learning-based dynamics, reinforcement learning, adaptive/robust control, ROS 2, hardware-in-the-loop, and a C++ production port.
