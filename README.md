# Intelligent Autonomous Mobile Robot with Integrated Visual &amp; Sensor-Based Navigation 
# 🤖 Intelligent Autonomous Mobile Robot with Integrated Visual & Sensor-Based Navigation

An open-source robotics platform built using ROS2 Humble, designed for adaptive navigation, SLAM, and vision-based object tracking. This project leverages low-cost hardware and powerful software to build a scalable educational and research robot capable of navigating dynamic environments.

---

## 📌 Table of Contents
- [Overview](#overview)
- [Key Features](#key-features)
- [Hardware Components](#hardware-components)
- [Software Stack](#software-stack)
- [Architecture](#architecture)
- [Setup & Installation](#setup--installation)
- [Simulation (Gazebo + RViz2)](#simulation-gazebo--rviz2)
- [Results](#results)
- [Contributors](#contributors)
- [License](#license)

---

## 🧠 Overview
This project demonstrates the development of an Autonomous Mobile Robot (AMR) using a split-compute architecture (Raspberry Pi 4B and ESP32). The system integrates:
- SLAM using LiDAR & IMU
- YOLO-based object detection
- Teleoperation and autonomous path planning
- ROS2 Navigation stack
- Simulation using Gazebo and visualization with RViz2

---

## 🚀 Key Features
- **Teleoperation & Autonomous Modes**
- **SLAM with Real-time Mapping**
- **A\* and RRT Path Planning**
- **YOLO-based Object Detection**
- **Gesture Control Interface**
- **ROS2 Parameter Tuning**
- **Live Visualization in RViz2**

---

## 🔩 Hardware Components
| Component                    | Role                              |
|-----------------------------|-----------------------------------|
| Raspberry Pi 4B (8GB RAM)   | High-level planning & perception  |
| ESP32-WROOM-32E             | Real-time motor & sensor control  |
| YDLiDAR X4                  | 2D LiDAR for SLAM & Obstacle Avoidance |
| Lenovo 300 FHD Webcam       | Object Detection via YOLO         |
| MPU-6050 IMU                | Orientation & Motion Tracking     |
| L298N Motor Driver          | Motor actuation                   |
| SparkFun DG01D-E Motors     | Differential Drive                |

---

## 💻 Software Stack
- **OS**: Ubuntu Server 22.04 (64-bit)
- **Middleware**: ROS2 Humble Hawksbill
- **SLAM**: slam_toolbox
- **Navigation**: Nav2 Stack
- **Simulation**: Gazebo (Ignition), RViz2
- **Security**: SROS2 (DDS Security)
- **Firmware Interface**: rosserial for ESP32

---

## 🧩 Architecture

![Block Diagram](path/to/your/diagram.png)

The architecture follows a layered approach:
- Sensor layer: LiDAR, IMU, Camera
- Compute layer: Raspberry Pi 4B + ESP32
- Middleware: ROS2 DDS communication
- Control layer: PID & MPC for motor precision
- UI: Web GUI & RViz2

---

## ⚙️ Setup & Installation

```bash
# Install ROS2 Humble
sudo apt install ros-humble-desktop

# Clone the repository
git clone https://github.com/Aarya-Mourya/Autonomous-Mobile-Robot/darya-amr.git
cd darya-ros2

# Install dependencies
rosdep install --from-paths src --ignore-src -r -y

# Build workspace
colcon build

# Source setup
source install/setup.bash

# Launch simulation
ros2 launch amr_sim gazebo_sim.launch.py

# Launch RViz2
ros2 launch amr_viz rviz.launch.py
