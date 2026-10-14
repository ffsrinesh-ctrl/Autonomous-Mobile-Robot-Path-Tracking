# Autonomous Mobile Robot Path Tracking and Dynamic Obstacle Avoidance

A MATLAB and Simulink project that compares Pure Pursuit and Stanley controllers for mobile robot path tracking, with a predictive safety supervisor to help the robot respond to static and moving obstacles.

## Overview

A mobile robot needs to follow its planned path while responding to obstacles in its environment. This becomes more challenging when an obstacle blocks the route or moves while the robot is approaching it.

This project uses a differential-drive robot model to study these challenges through simulation. Pure Pursuit and Stanley controllers are implemented to guide the robot along a predefined reference path. A predictive safety supervisor evaluates candidate motion commands and can adjust the robot's speed or turning direction when a potential collision risk is detected.

The main goal is to understand how the two controllers behave under different obstacle conditions and identify areas where the navigation system can be improved.

## Objectives

- Develop a differential-drive mobile robot model in MATLAB and Simulink.
- Implement Pure Pursuit and Stanley path-tracking controllers.
- Integrate a predictive safety supervisor.
- Test the system under static and dynamic obstacle conditions.
- Compare tracking accuracy, obstacle clearance, collision status, and goal-reaching performance.
- Identify limitations and possible improvements.

## How the System Works

### Pure Pursuit Controller

Pure Pursuit selects a look-ahead point on the reference path and calculates a turning command to guide the robot towards that point. Its behaviour depends partly on the look-ahead distance and the robot's motion limits.

### Stanley Controller

The Stanley controller uses heading error and cross-track error to correct the robot's orientation and lateral deviation from the reference path. Its commands are adapted to the differential-drive robot model used in this project.

### Predictive Safety Supervisor

The safety supervisor evaluates candidate motion commands by predicting the robot's movement relative to nearby obstacles. When a potential collision risk is identified, it can consider alternatives such as reducing speed or changing the turning command.

The supervisor is intended to reduce predicted collision risk; it does not guarantee collision-free navigation in every situation.

## Simulation Scenarios

The project considers five scenarios:

1. **Obstacle-free navigation** — evaluates baseline path-tracking behaviour.
2. **Static obstacle** — examines the robot's response to a stationary obstacle.
3. **Slower-moving obstacle** — tests navigation around an obstacle moving slower than the robot's nominal speed.
4. **Equal-speed obstacle** — examines the interaction with an obstacle moving at the same nominal comparison speed.
5. **Faster-moving obstacle** — evaluates the response to an obstacle moving faster than the robot's nominal speed.

## Performance Evaluation

The simulation can be evaluated using the following metrics, where supported by the recorded data:

- **Cross-track error:** Measures the robot's deviation from the reference path.
- **Root mean square error (RMSE):** Summarises tracking error over the evaluation interval.
- **Maximum cross-track error:** Identifies the largest absolute tracking deviation.
- **Minimum obstacle clearance:** Measures the closest separation between the robot and an obstacle.
- **Collision status:** Records the result of the implemented collision-detection method.
- **Goal-reaching status:** Indicates whether the robot reaches the configured goal region.

The results should be interpreted together. A robot may avoid an obstacle but fail to reach its goal, while accurate path tracking alone does not establish safe navigation.

## Technology Stack

- MATLAB
- Simulink
- MATLAB scripts and supporting functions used by the implementation

## Project Files

The repository includes `dynamicObstacleDashboard.zip`, which contains the project files.

## How to Run

1. Clone or download this repository.
2. Extract `dynamicObstacleDashboard.zip` into a working directory.
3. Open MATLAB and set the Current Folder to the extracted project directory.
4. Locate the main MATLAB script (`.m`) or Simulink model (`.slx`).
5. Review any setup instructions and required parameters included with the project files.
6. Run the script or open and run the Simulink model.
7. Review the generated trajectories, recorded data, and dashboard outputs, if included.

The exact startup file and any additional toolbox requirements depend on the contents of the project archive.

## Limitations

- The results are based on simulation and may differ from real-world robot behaviour.
- Obstacle prediction depends on the motion assumptions used by the model.
- The available candidate commands may not cover every possible safe movement.
- Controller performance depends on the path geometry and parameter settings.
- Physical-robot validation and formal safety verification are not claimed unless separately implemented.

## Future Improvements

- Test more obstacle positions and movement patterns.
- Improve prediction of dynamic-obstacle trajectories.
- Tune controller and safety-supervisor parameters.
- Evaluate performance under different initial conditions.
- Test the system on a physical differential-drive robot.

## Academic Context

Developed as part of the **Dynamics and Control of Robotics (22AIE441)** coursework at Amrita Vishwa Vidyapeetham, Amaravati Campus.
