# Visualization of Performance Indicators for Unmanned Aerial Vehicles

This repository contains the project "Visualization of Performance Indicators for Unmanned Aerial Vehicles (UAV)", focusing on creating an interactive dashboard to monitor and analyze UAV performance.

## Table of Contents

- [Introduction](#introduction)
- [Objectives](#objectives)
- [Dataset Description](#dataset-description)
  - [Use of the Dataset](#use-of-the-dataset)
  - [Content of the Data](#content-of-the-data)
  - [Tables Description](#tables-description)
  - [Type of File](#type-of-file)
- [Measures/KPIs](#measureskpis)
- [Visuals/Graphs](#visualsgraphs)
- [References](#references)
- [License](#license)

## Introduction

This project aims to provide a comprehensive overview of the operational performance and mission success of UAVs by visualizing various performance indicators. The data is generated in a virtual environment using QGroundControl, PX4 Autopilot, and Gazebo.

## Objectives

- **Operational Efficiency**: Track fuel, battery life, and flying time to ensure missions are completed efficiently.
- **Maintenance and Predictive Analysis**: Predict maintenance needs and reduce downtime by monitoring performance indicators.
- **Safety and Reliability**: Monitor UAV safety and health to minimize accidents and ensure safe operations.

## Dataset Description

### Use of the Dataset

The dataset can be used for:

- Developing and evaluating algorithms for UAV sensing, control, and mission scheduling.
- Training machine learning models for tasks such as path planning, SLAM, and object detection.
- Analyzing and improving the resilience of UAV systems and navigation.

### Content of the Data

The dataset includes the following categories of data:

- **Sensor Data**: IMU readings, GPS coordinates, lidar scans, and environmental sensor data.
- **Control Commands**: Throttle, yaw, pitch, and roll commands sent to the UAV.
- **Flight Logs**: Detailed records of UAV behavior, navigation, and system performance.

### Tables Description

#### Control Commands

- **Timestamp**: Time reference associated with data collected during flight.
- **roll, pitch, heading**: Rotations and direction of the UAV.
- **rollRate, pitchRate, yawRate**: Rotation rates around respective axes.
- **groundSpeed, climbRate**: Horizontal speed over the ground and vertical ascent/descent rate.
- **throttlePct**: Throttle percentage.
- **setpoint.roll, setpoint.pitch, setpoint.yaw**: Desired roll, pitch, and yaw angles.
- **setpoint.rollRate, setpoint.pitchRate, setpoint.yawRate**: Desired rotation rates.

#### Sensor Data

- **Timestamp**: Time reference.
- **altitudeRelative, altitudeAMSL**: Relative and AMSL altitude.
- **altitudeTuning**: Altitude tuning parameters.
- **flightDistance, flightTime**: Distance traveled and flight duration.
- **distanceToHome, distanceToGCS**: Distance to home point and ground control station.
- **missionItemIndex**: Index of mission items.
- **headingToNextWP, headingToHome**: Heading directions.

#### Local Position

- **Timestamp**: Time reference.
- **localPosition.x, localPosition.y, localPosition.z**: Position coordinates.
- **localPosition.vx, localPosition.vy, localPosition.vz**: Velocity components.
- **localPositionSetpoint.x, localPositionSetpoint.y, localPositionSetpoint.z**: Setpoint positions.
- **localPositionSetpoint.vx, localPositionSetpoint.vy, localPositionSetpoint.vz**: Setpoint velocities.

#### ESC Status

- **Timestamp**: Time reference.
- **escStatus.rpm1, escStatus.rpm2, escStatus.rpm3, escStatus.rpm4**: RPM values of motors.
- **escStatus.current1, escStatus.current2, escStatus.current3, escStatus.current4**: Current drawn by motors.
- **escStatus.voltage1, escStatus.voltage2, escStatus.voltage3, escStatus.voltage4**: Voltage measurements of motors.

### Type of File

- **Log Data Files**: PX4 Autopilot and QGroundControl create log files with the extension ".ulg".

## Measures/KPIs

### Control Commands

1. **Total Pitch**: `SUM([pitch])`
2. **Average Ground Speed**: `AVERAGE([groundSpeed])`
3. **Maximum Climb Rate**: `MAX([climbRate])`
4. **Total Throttle Percentage**: `SUM([throttlePct])`
5. **Average Pitch**: `AVERAGE('Control commands'[pitch])`
6. **Average Roll**: `AVERAGE('Control commands'[roll])`
7. **Average Heading**: `AVERAGE('Control commands'[heading])`

### Sensor Data

1. **Total Flight Time**: `SUM(dataset[flightTime])`
2. **Average Altitude Relative**: `AVERAGE(dataset[altitudeRelative])`
3. **Total Distance Flown**: `SUM(dataset[flightDistance])`
4. **Average Distance to Home**: `AVERAGE(dataset[distanceToHome])`
5. **Maximum Altitude AMSL**: `MAX(dataset[altitudeAMSL])`
6. **Minimum Altitude Tuning**: `MIN(dataset[altitudeTuning])`
7. **Average Heading to Next Waypoint**: `AVERAGE(dataset[headingToNextWP])`

### Local Position

1. **Maximum Altitude**: `MAX('localPosition.z')`
2. **Average Velocity**: `AVERAGE('localPosition.vx')`
3. **Acceleration**: `DIVIDE(('Local Position'[localPosition.vz] - LAG('('Local Position', [localPosition.vz], 1)), 'Timestamp' - LAG('('Local Position', 'Timestamp', 1))`
4. **Total Time Spent**: `MAX('Timestamp') - MIN('Timestamp')`
5. **Minimum Velocity**: `MIN('localPosition.vx')`
6. **Maximum Velocity**: `MAX('localPosition.vx')`

### ESC Status

1. **Total Operating Time**: `MAX('Timestamp') - MIN('Timestamp')`
2. **Average RPM for Each Motor**: `AVERAGE('escStatus.rpm1')`, `AVERAGE('escStatus.rpm2')`, `AVERAGE('escStatus.rpm3')`, `AVERAGE('escStatus.rpm4')`
3. **Voltage Drop**: `MAX('escStatus.voltage1') - MIN('escStatus.voltage1')`, `MAX('escStatus.voltage2') - MIN('escStatus.voltage2')`, `MAX('escStatus.voltage3') - MIN('escStatus.voltage3')`, `MAX('escStatus.voltage4') - MIN('escStatus.voltage4')`
4. **Total Current Consumed**: `SUM('escStatus.current1') + SUM('escStatus.current2') + SUM('escStatus.current3') + SUM('escStatus.current4')`
5. **RPM Deviation from Setpoint**: `AVERAGE([escStatus.rpm1] - [SetpointRPM1])`, `AVERAGE([escStatus.rpm2] - [SetpointRPM2])`, `AVERAGE([escStatus.rpm3] - [SetpointRPM3])`, `AVERAGE([escStatus.rpm4] - [SetpointRPM4])`

## Visuals/Graphs

### Control Commands

1. **Line Charts**: Roll Rate, Pitch Rate, Yaw Rate.
2. **Line Chart for Multivariate Time Series**: Roll, Pitch, and Heading.
3. **Histograms**: Roll, Pitch, Heading, Roll Rate, Pitch Rate, Yaw Rate, Ground Speed, Climb Rate, Throttle Percentage.
4. **Scatter Plots**: Roll vs. Pitch, Ground Speed vs. Climb Rate.
5. **Filter Controls and Slicers**: Interactive data filtering.

### Sensor Data

1. **Line Chart**: Flight Time vs. Distance.
2. **Scatter Plot**: Altitude vs. Distance.
3. **Line Chart**: Altitude over Time.
4. **Bar Chart**: Distance to Home.
5. **KPI Cards**: Average altitude, total flight time, maximum distance covered.

### Local Position

1. **Line Charts**: x, y, z coordinates vs. Timestamp.
2. **Scatter Plots**: localPosition.x vs. localPosition.y, localPosition.x vs. localPosition.z, localPosition.y vs. localPosition.z.
3. **Velocity Histograms**: localPosition.vx, localPosition.vy, localPosition.vz.

### ESC Status

1. **Time Series Line Chart**: RPM1, RPM2, RPM3, RPM4.
2. **Multi-line Chart**: RPM, Current, and Voltage for each component.
3. **Scatter Plot**: RPM vs. Current.
4. **Box-and-Whisker Plots**: RPM, Current, Voltage.

## References

1. Whelan, J., Almehmadi, A. and El-Khatib, K., 2022. Artificial intelligence for intrusion detection systems in unmanned aerial vehicles. Computers and Electrical Engineering, 99, p.107784.
2. Mohsan, S.A.H., Khan, M.A., Noor, F., Ullah, I. and Alsharif, M.H., 2022.

