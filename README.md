# 🎯 Perspective Projection of a Human Pose in 3D Space

This project demonstrates the application of **perspective projection** to a 3D human pose model using Python. It simulates how a camera rotating around the subject captures 2D projected images from different angles, mimicking real-world depth and perspective.

---

## 🧠 Overview

**Perspective projection** is a fundamental technique in computer graphics used to convert 3D coordinates into a 2D plane, providing the illusion of depth and realism. This implementation focuses on:

- Modeling a simple human pose as 3D points and joint connections.
- Simulating a camera rotating in a horizontal circle around the pose.
- Projecting the 3D joints to 2D space from different camera angles (every 45°).
- Visualizing the pose projection for each rotation.

---

## 🧍‍♂️ Human Pose Representation

The pose is defined as a set of 3D points (X, Y, Z) with indexes describing body parts:

| Joint | X   | Y    | Z    |
|-------|-----|------|------|
| P1    | 0   | 0    | 0    |
| P2    | 6.5 | 2.5  | -2.5 |
| P3    | 6.5 | 2.5  | -7.5 |
| P4    | 6.5 | -2.5 | -2.5 |
| P5    | 6.5 | -2.5 | -7.5 |
| P6    | 6.5 | 0    | 0    |
| P7    | 6.5 | 5    | 0    |
| P8    | 6.5 | 5    | 2.5  |
| P9    | 6.5 | -2.5 | 2.5  |
| P10   | 6.5 | 5    | -2.5 |
| P11   | 6.5 | -2.5 | -2.5 |

**Connected Body Parts:**

- `larm_idx  = [1, 6, 8, 9]` → Left arm  
- `rarm_idx  = [1, 6, 10, 11]` → Right arm  
- `lleg_idx  = [1, 2, 3]` → Left leg  
- `rleg_idx  = [1, 4, 5]` → Right leg  
- `torso_idx = [1, 6]` → Torso  
- `head_idx  = [6, 7]` → Head  

> All points are in 3D space using a right-handed coordinate system.

---

## 📷 Camera Settings

- Camera starts at location: `[25, 0, 0]`
- Rotates around the **Y-axis** in 45° increments (i.e., π/4 radians)
- Captures the projected 2D image at each of the 8 positions (360° / 45°)

---

## 🧮 Perspective Projection

### Projection Formula:
Given camera position and orientation, each 3D point is projected onto a 2D image plane using:

[x_proj, y_proj] = [f * (X / Z), f * (Y / Z)]

Where:
- `f` is the focal length (fixed or proportional to distance from the camera)
- `X, Y, Z` are coordinates after transforming into the camera coordinate system
- A 4x4 transformation matrix is used to rotate and translate the 3D points.

---

## 📌 Features

- Full implementation of perspective projection
- Custom human pose visualization
- Dynamic camera rotation and 2D image generation
- Easy-to-understand code and modular structure
- Visualization using `matplotlib`
نسخ
تحرير
