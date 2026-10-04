# 🤖 Build an Autonomous Mecanum-Wheel Robot from Scratch

> **Yun Robotics Lab — Project 01**

A complete robotics project to design, simulate, and develop an **autonomous Mecanum-wheel mobile robot from scratch** using ROS 2.

The project covers the complete development process, from **3D mechanical design and robot modeling** to **simulation, SLAM, navigation, control, and autonomous operation**.

---

## 📌 Project Overview

This project is part of the **Yun Robotics Lab** robotics engineering series.

The goal is to build an autonomous Mecanum-wheel robot while documenting the entire development process through YouTube videos and GitHub.

### Main Goals

* Design the robot in Fusion 360
* Create the robot model using URDF/Xacro
* Build a ROS 2 robot package
* Simulate the robot in Gazebo
* Add sensors and sensor simulation
* Implement Mecanum-wheel motion control
* Perform mapping and localization
* Implement autonomous navigation
* Develop waypoint and path-following capabilities
* Build a complete autonomous robot system

---

## 🧠 Technologies

| Category           | Technology   |
| ------------------ | ------------ |
| Operating System   | Ubuntu 22.04 |
| Robotics Framework | ROS 2 Humble |
| Simulation         | Gazebo       |
| 3D Design          | Fusion 360   |
| Robot Description  | URDF / Xacro |
| Navigation         | Nav2         |
| Mapping            | SLAM Toolbox |
| Visualization      | RViz2        |
| Programming        | Python / C++ |
| Version Control    | Git / GitHub |

---

## 🤖 Robot Concept

The robot uses **four Mecanum wheels** to provide omnidirectional movement.

### Main Motion

* Forward / backward
* Left / right strafing
* Rotation
* Diagonal movement
* Combined translation + rotation

### Target Robot

```text
                    FRONT
                      ↑

             ┌─────────────────┐
             │                 │
      FL ◉   │                 │   ◉ FR
             │      ROBOT      │
             │                 │
      RL ◉   │                 │   ◉ RR
             │                 │
             └─────────────────┘

          ◉ = Mecanum Wheel
```

---

## 🏗️ System Architecture

The project follows a layered robotics architecture:

```text
┌──────────────────────────────────────┐
│          Autonomous Mission          │
│       Navigation / Waypoints         │
├──────────────────────────────────────┤
│                Nav2                  │
│   Planner / Controller / Recovery    │
├──────────────────────────────────────┤
│       Localization / Mapping         │
│        SLAM Toolbox / AMCL           │
├──────────────────────────────────────┤
│          Robot Perception            │
│       LiDAR / IMU / Odometry         │
├──────────────────────────────────────┤
│         Robot Control Layer          │
│      Mecanum Kinematics / PID        │
├──────────────────────────────────────┤
│           ROS 2 Robot Model          │
│       URDF / Xacro / TF2             │
├──────────────────────────────────────┤
│       Gazebo Simulation / World      │
├──────────────────────────────────────┤
│       Robot Mechanical Design        │
│              Fusion 360              │
└──────────────────────────────────────┘
```

---

## 🧩 ROS 2 Package Structure

The project will be organized into multiple ROS 2 packages:

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

### Package Responsibilities

| Package                      | Responsibility                       |
| ---------------------------- | ------------------------------------ |
| `mecanum_robot_description`  | URDF/Xacro, meshes, TF               |
| `mecanum_robot_gazebo`       | Gazebo world and simulation          |
| `mecanum_robot_control`      | Wheel control and Mecanum kinematics |
| `mecanum_robot_bringup`      | Launch and system startup            |
| `mecanum_robot_navigation`   | Nav2 configuration                   |
| `mecanum_robot_localization` | Localization                         |
| `mecanum_robot_slam`         | Mapping                              |
| `mecanum_robot_interfaces`   | Custom messages/services if required |

---

## 🌳 TF Tree

The target TF structure is:

```text
map
 └── odom
      └── base_footprint
           └── base_link
                ├── laser_link
                ├── imu_link
                ├── camera_link
                ├── front_left_wheel_link
                ├── front_right_wheel_link
                ├── rear_left_wheel_link
                └── rear_right_wheel_link
```

The exact TF structure may change during development.

---

## 📡 Sensors

The initial simulated robot will include:

* 2D LiDAR
* IMU
* Wheel odometry
* RGB camera *(optional / future)*
* Depth camera *(optional / future)*

### Sensor Purpose

| Sensor         | Purpose                           |
| -------------- | --------------------------------- |
| LiDAR          | Mapping and obstacle detection    |
| IMU            | Orientation and motion estimation |
| Wheel Encoders | Odometry                          |
| RGB Camera     | Vision                            |
| Depth Camera   | 3D perception                     |

---

## 🌎 Simulation Environment

The robot will initially be developed in simulation before moving toward physical hardware.

### Simulation Components

```text
Robot Model
     ↓
Gazebo
     ↓
Sensors
     ↓
ROS 2 Topics
     ↓
SLAM / Localization
     ↓
Nav2
     ↓
Velocity Commands
     ↓
Robot Controller
```

The first environment will be a small indoor/warehouse-style environment containing:

* Walls
* Obstacles
* Open navigation areas
* Narrow passages
* Navigation targets

---

# 🎬 12-Episode Roadmap

## Phase 1 — Robot Design

### Episode 01 — Project Planning

Define the robot concept, requirements, architecture, ROS 2 stack, and development roadmap.

### Episode 02 — Design the Robot in Fusion 360

Create the mechanical design of the Mecanum-wheel robot.

### Episode 03 — Build the Robot Model with URDF/Xacro

Convert the mechanical design into a ROS 2 robot description.

---

## Phase 2 — Simulation

### Episode 04 — Simulate the Robot in Gazebo

Create the simulation environment and spawn the robot.

### Episode 05 — Add Sensors

Add LiDAR, IMU, camera, and odometry simulation.

### Episode 06 — Control the Mecanum Robot

Implement Mecanum-wheel kinematics and robot velocity control.

---

## Phase 3 — Mapping & Localization

### Episode 07 — Build a Map with SLAM

Use LiDAR and SLAM Toolbox to create a map.

### Episode 08 — Localize the Robot

Implement localization and test robot pose estimation.

---

## Phase 4 — Autonomous Navigation

### Episode 09 — Setup ROS 2 Navigation

Configure Nav2 for the Mecanum robot.

### Episode 10 — Autonomous Navigation

Test path planning, obstacle avoidance, and goal navigation.

### Episode 11 — Waypoints & Autonomous Missions

Create waypoint-based autonomous missions.

### Episode 12 — Complete Autonomous Robot

Combine all systems into one complete autonomous Mecanum-wheel robot.

---

# 📁 Repository Structure

```text
autonomous-mecanum-robot/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── docs/
│   ├── architecture/
│   ├── robot-requirements/
│   ├── ros2-stack/
│   ├── tf-tree/
│   └── sensors/
│
├── src/
│   ├── mecanum_robot_description/
│   ├── mecanum_robot_gazebo/
│   ├── mecanum_robot_control/
│   ├── mecanum_robot_bringup/
│   ├── mecanum_robot_navigation/
│   ├── mecanum_robot_localization/
│   ├── mecanum_robot_slam/
│   └── mecanum_robot_interfaces/
│
├── worlds/
├── models/
├── config/
├── launch/
├── scripts/
└── media/
```

---

# 🚀 Development Workflow

The development process follows:

```text
Idea
 ↓
Requirements
 ↓
Mechanical Design
 ↓
URDF / Xacro
 ↓
Gazebo Simulation
 ↓
Sensor Integration
 ↓
Robot Control
 ↓
SLAM
 ↓
Localization
 ↓
Navigation
 ↓
Autonomous Mission
 ↓
Final Robot
```

---

# 📊 Project Status

| Stage              | Status         |
| ------------------ | -------------- |
| Project Planning   | 🟡 In Progress |
| Robot Requirements | ⚪ Planned      |
| Fusion 360 Design  | ⚪ Planned      |
| URDF/Xacro         | ⚪ Planned      |
| Gazebo Simulation  | ⚪ Planned      |
| Sensor Integration | ⚪ Planned      |
| Mecanum Control    | ⚪ Planned      |
| SLAM               | ⚪ Planned      |
| Localization       | ⚪ Planned      |
| Nav2               | ⚪ Planned      |
| Autonomous Mission | ⚪ Planned      |
| Final Demo         | ⚪ Planned      |

---

# 🎥 YouTube Series

**Yun Robotics Lab**

> Build an Autonomous Mecanum-Wheel Robot from Scratch

The YouTube series documents the development process from the initial design to the final autonomous robot.

Episodes will be linked here as they are published.

```text
Episode 01 — Project Planning
Episode 02 — Fusion 360 Design
Episode 03 — URDF/Xacro
Episode 04 — Gazebo Simulation
Episode 05 — Sensor Integration
Episode 06 — Mecanum Control
Episode 07 — SLAM
Episode 08 — Localization
Episode 09 — Nav2
Episode 10 — Autonomous Navigation
Episode 11 — Autonomous Missions
Episode 12 — Final Robot
```

---

# 📚 Documentation

Detailed documentation will be maintained in the `docs/` directory.

Topics include:

* Robot requirements
* Mechanical design
* ROS 2 architecture
* Package architecture
* TF tree
* Sensor configuration
* Mecanum kinematics
* Robot control
* Gazebo simulation
* SLAM
* Localization
* Nav2
* Autonomous missions

---

# 🎯 Final Goal

The final goal is to create a complete autonomous Mecanum-wheel robot that can:

```text
        Human
          │
          │ Goal
          ▼
   ┌─────────────┐
   │   Mission   │
   │   Manager   │
   └──────┬──────┘
          ↓
        Nav2
          ↓
   Path Planning
          ↓
   Obstacle Avoidance
          ↓
    Mecanum Control
          ↓
       Robot
          ↓
      Sensors
          └──────────► Environment
```

The project is intended to demonstrate the complete workflow of building a modern autonomous mobile robot using **ROS 2, Gazebo, Nav2, SLAM, and Mecanum-wheel kinematics**.

---

## 👨‍💻 About Yun Robotics Lab

**Yun Robotics Lab** is a personal robotics engineering and learning project focused on:

* Autonomous Mobile Robots
* ROS 2
* Robot Simulation
* Robot Control
* Robot Navigation
* Robot Learning
* AI / VLA
* Mobile Manipulation

This project is built as both a **learning platform and engineering portfolio**.

---

## 📌 Project Status

**Current Phase:** Step 1 — Project Planning
**Project:** Autonomous Mecanum-Wheel Robot
**Series:** 01
**Lab:** Yun Robotics Lab
