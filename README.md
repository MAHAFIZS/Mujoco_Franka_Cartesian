# 🦾 MuJoCo Franka Cartesian Control – Gesture-Based Interface

This repository is part of my Master's Thesis at **FAU Erlangen-Nürnberg**. It focuses on controlling a **Franka Emika Panda** robot using **gesture-based teleoperation** in Cartesian space, combining **MuJoCo simulation**, **IM Blocks interface**, and **Python-based control scripts**.

## 🎯 Project Objective

Design an **intuitive control system** that allows a user to move a Franka robot’s end-effector in **X/Y/Z Cartesian space**, rotate the gripper, and control the fingers — using only **gesture commands**. The system includes:

- A **gesture-driven visual menu** in iM Blocks
- A Python-based MuJoCo controller
- Real-time motion mapped from gestures to Cartesian commands

---

## 🧩 Project Structure

```bash
📂 mujoco_script.py          # Main Python controller (Cartesian + grasping)
📂 cpMuJoCo.cs               # iM Blocks C# interface with image-based gesture menu
📂 menus/                    # Gesture-based menu images (e.g., cartesianx.png, finger.png)
📂 README.md                 # This file
📂 LICENSE                   # MIT License

🖼️ Gesture UX Interface (IM Blocks)
The gesture control system uses a scroll-lock-execute approach:

Scroll Gesture (↓) – Navigate menu options

Lock Gesture (✊) – Select an axis or function (e.g., X, Y, Z, Gripper, Finger)

Action Gestures (→/←) – Move in + / − direction (or open/close gripper)

Menu Structure:
Menu.png – Main menu

cartesianx.png, cartesiany.png, cartesianz.png – Axis-specific

gripper.png, finger.png – Gripper and finger control

Commands are mapped via UDP from iM Blocks to Python (ports 5005 → 5006).

🧠 Features
✅ Gesture-based Cartesian control using Jacobian inverse kinematics

✅ Gripper rotation and finger control (open/close)

✅ Simulated pick-and-place using goto_box() and pick_box() routines

✅ Modular Python code for real-time control and visual feedback

✅ Robust visual gesture UI implemented in C# (cpMuJoCo.cs)

🔧 Requirements
MuJoCo

Python 3.12+

numpy, mujoco, pygame, socket libraries

iM Blocks with custom cpMuJoCo and MuJoCoControl blocks

🔬 Related Work
This simulation project is complemented by a parallel IMU/EMG data pipeline:

🔗 IMU Bias & Noise Analysis Project

🤖 Real Robot Integration
The same gesture control system is being extended to real-world execution using the Franka Emika Panda robot with the cpFranka.cs interface.

📜 License
This project is open-source under the MIT License. You are free to use, modify, and distribute with attribution.