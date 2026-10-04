# 🤖 Autonomous Mecanum-Wheel Robot

> **Yun Robotics Lab — Project 01**

Building an **autonomous four-wheel Mecanum robot from scratch** using ROS 2, Gazebo, STM32, LiDAR, IMU, and Nav2.

The project covers the complete robotics workflow:

**Design → Simulation → Control → SLAM → Localization → Navigation → Autonomous Mission**

---

## 🎯 Project Goal

Build a compact and modular Mecanum-wheel robot capable of:

* Omnidirectional movement
* Wheel odometry
* LiDAR-based mapping
* Robot localization
* Autonomous navigation
* Obstacle avoidance
* Waypoint-based missions

The project will be developed **simulation-first**, followed by a physical prototype.

---

## 🤖 Robot Specification

| Component     | Specification             |
| ------------- | ------------------------- |
| Drive         | 4 × Mecanum wheels        |
| Wheel         | ~80 mm                    |
| Chassis       | 2-floor aluminum          |
| Chassis size  | ~450 × 250 × 250 mm       |
| Motor         | JGA25-370 + encoder, 12 V |
| Main computer | Raspberry Pi 4B           |
| Motor control | 2 × STM32F103C8T6         |
| LiDAR         | RPLIDAR A1M8              |
| IMU           | BNO055                    |
| Camera        | Raspberry Pi Camera       |
| Battery       | 12 V LiPo                 |
| Motor driver  | TBD                       |
| DC/DC         | TBD                       |

> Dimensions and hardware marked **TBD** will be finalized during the design stage.

---

## 🏗️ System Architecture

<img src="docs/images/System_Architecture_AMR_Mecanum_wheel" alt="system_architecture" width="500">

### Software Stack

* Ubuntu 22.04
* ROS 2 Humble
* Gazebo Fortress
* Nav2
* SLAM Toolbox
* RViz2
* URDF / Xacro
* Python / C++
* STM32

---

## 📦 ROS 2 Packages

```text
mecanum_robot_ws/
└── src/
    ├── mecanum_robot_description/
    ├── mecanum_robot_gazebo/
    ├── mecanum_robot_control/
    ├── mecanum_robot_bringup/
    ├── mecanum_robot_navigation/
    ├── mecanum_robot_localization/
    ├── mecanum_robot_slam/
    └── mecanum_robot_interfaces/
```

---

## 🎬 12-Episode Roadmap

| #  | Episode                   |
| -- | ------------------------- |
| 01 | Project Planning          |
| 02 | Fusion 360 Robot Design   |
| 03 | URDF / Xacro              |
| 04 | Gazebo Simulation         |
| 05 | Sensor Integration        |
| 06 | Mecanum Motor Control     |
| 07 | SLAM Mapping              |
| 08 | Localization              |
| 09 | ROS 2 Navigation / Nav2   |
| 10 | Autonomous Navigation     |
| 11 | Waypoints & Missions      |
| 12 | Complete Autonomous Robot |

---

## 📁 Repository

```text
autonomous-mecanum-robot/
├── README.md
├── docs/
├── src/
├── config/
├── launch/
├── worlds/
├── models/
├── scripts/
└── media/
```

Detailed documentation:

* `docs/requirements/`
* `docs/architecture/`
* `docs/mechanical-design/`
* `docs/electrical/`
* `docs/ros2-stack/`
* `docs/sensors/`

---

## 📊 Project Status

**Current Phase:** Step 1 — Project Planning 🟡

* [x] Project concept
* [x] Initial hardware list
* [x] Initial architecture
* [x] ROS 2 stack
* [x] 12-episode roadmap
* [ ] Final hardware specifications
* [ ] Fusion 360 design
* [ ] URDF/Xacro
* [ ] Gazebo simulation
* [ ] Autonomous navigation

---

## 👨‍💻 Yun Robotics Lab

**Yun Robotics Lab** is a personal robotics engineering project focused on:

**ROS 2 · Autonomous Robots · Simulation · Robot Control · Navigation · Robot Learning · AI/VLA**

> **Build. Simulate. Control. Learn. Deploy.**
