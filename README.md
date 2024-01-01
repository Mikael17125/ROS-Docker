# ROS-Docker Setup and Documentation

## Overview

This documentation provides an overview of prerequisites, instructions on how to run the ROS-Docker workspace, and explanations of environment variables and parameters used in the project. The ROS-Docker project is designed for mapping and navigation tasks, integrating various hardware components and software modules.

## Prerequisites

### Hardware
- [ ] Power Distribution Board
- [ ] Sensors
  - [ ] Camera
  - [ ] Inertial Measurement Unit (IMU)
  - [ ] Odometer
  - [ ] Lidar
- [ ] Robot's Model
- [ ] Computer
- [ ] Sensor Module Board

### Software
- [ ] ROS Framework
- [ ] Filtering Sensor Module
- [ ] Feature Extraction Module
- [ ] Pose Estimation Module
- [ ] Path Planning Module
- [ ] Interface Module
- [ ] Docker

## How to Run

1. Create a workspace folder:

   ```bash
   mkdir -p ~/movel_ws/src
   cd ~/movel_ws/src
   ```

2. Clone the project:

   ```bash
   git clone https://github.com/Mikael17125/movel-test.git .
   ```

3. Build Docker container images:

   ```bash
   cd ~/movel_ws/src/path_generator/
   docker build -t path-generator:1.0 .
   ```

   ```bash
   cd ~/movel_ws/src/rviz_visualizer/
   docker build -t rviz-visualizer:1.0 .
   ```

   ```bash
   cd ~/movel_ws/src/path_reduction/
   docker build -t path-reduction:1.0 .
   ```

4. Start the program:

   ```bash
   docker-compose up -d
   ```

## Documentation and Parameters

### Environment Variables

- `N_POINT`: Number of points in the reduced path.
- `SPLINE`: Spline method selection (0: Lagrange Method, 1: Cubic Spline Method).
- `COORD`: Spline coordinate selection.

### Example ENV Variable Usage

```bash
N_POINT=10
SPLINE=0
COORD=1
```

### Coordinate Definition

```python
dt = np.array([0,1,2,3,4])
x = np.array([-3, 2, -2, -1, 1])
y = np.array([3, 2,  1, -1, 5])

dt1 = np.array([0,1,2,3,4])
x1 = np.array([0, 4, -2, 1, 0])
y1 = np.array([1, 2,  -4, 1, -3])
```

## Explanation

- [ ] The project employs Cubic Spline and Lagrange Interpolation methods for path reduction. Cubic Spline is chosen for its simplicity of calculation, numerical stability, and smoothness. Lagrange Interpolation is selected for its accuracy with higher-order polynomials.
- [ ] The sampling method is used for path filtering, where the original, filtered, and reduced paths are represented by green, red, and blue colors, respectively. This method is resource-intensive.

## Video Documentation

Watch the [Video Documentation on YouTube](https://www.youtube.com/watch?v=q5Tb2qVTZEU) for a visual walkthrough of the ROS-Docker project.
