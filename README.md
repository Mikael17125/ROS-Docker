# MOVEL-TEST

### A brief documentation on what prerequisite things need to be checked (hardware and software checks) before starting to do a mapping or navigation task

Hardware <br>
-----
- [ ] Power Distribution Board
- [ ] Sensor
  - [ ] Camera 
  - [ ] Inertial Measurment Unit (IMU)
  - [ ] Odometer
  - [ ] Lidar
- [ ] Robot's Model
  - This is so urgent too for analytical solution in example for calculating control system (ex : LQR, LQG, Model Predictive Control)
- [ ] Computer
- [ ] Sensor Module Board
  - Some sensor doesn't have serial port, so we have to made sensor module (example for IMU and Odometer) 

Software <br>
-----
- [ ] Framework
  - This urgently for controling all thread, and fast deploying
- [ ] Module
  - [ ] Filtering Sensor
    - Can be used sampling method for reduce dimension of the lidar sensor
    - Must be concern on odometer result, data may lead messy pose estimation
    - Can be used filtering method (example KF, EKF) for filtering the IMU sensor
  - [ ] Feature Extraction from Camera
    - For additional feature on Pose Estimation using Monte-Carlo or Adaptive Monte Carlo
  - [ ] Pose Estimation
    - Can be used Monte Carlo Method or Adaptive Monte Carlo
  - [ ] Path Planning
    - Must be concern with memmory usaged
  - [ ] Interface
    - This is simple but so urgent for monitoring
- [ ] Computer (Must be handled all proccessing)
