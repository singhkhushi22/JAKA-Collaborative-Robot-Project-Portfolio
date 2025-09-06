# 🤖 JAKA Collaborative Robot – Project Portfolio

Welcome to my **JAKA Cobot Project Portfolio**, where I combined everything I have learned and implemented with the **JAKA Collaborative Robot (6-DOF serial manipulator)**.

This repo is designed as both a **showcase for my work** and a **practical guide** for anyone who wants to understand and replicate these projects.

---

## 🏗 About JAKA Collaborative Robot

**JAKA (Just Always Keep Amazing)** cobots are **6-axis collaborative robots** widely used in industrial automation, assembly, and research.
They are safe to work around humans, easy to program, and flexible for multiple tasks.

### 🔑 Key Features:

* ✅ **6 DOF (Degrees of Freedom)** – similar to a human arm
* ✅ **High repeatability & accuracy**
* ✅ **Supports multiple motion types** – Joint, Linear, Circular
* ✅ **Easy integration with grippers, vision, and PLCs**
* ✅ **Safe for collaborative environments**

📸 Example photo of JAKA cobot in use:

```markdown
![JAKA Collaborative Robot](images/jaka-cobot-photo.jpg)
```

📽 Demo video of JAKA in action:

```markdown
[![Watch the Demo](images/video-thumbnail.png)](https://your-video-link.com)
```

---

## 1️⃣ Robot Mechanics Demonstration

This project connects **theory (mechanics)** with **real-world robotics** using JAKA.

### 🎯 Objectives

* Identify **links and joints** of a cobot
* Understand **6 DOF** configuration
* Visualize the mechanical motion

### 🛠 Technical Explanation

* **Links**: 7 (including base as Link 0, and tool mounting as Link 7)
* **Joints**: 6, all **rotary/revolute**
* **Configuration**: 6-DOF serial manipulator

#### Links

* Link 0 → Fixed Base
* Links 1–6 → Arm segments
* Link 7 → End-effector mount

#### Joints

* Base rotation joint
* Shoulder rotation joint
* Elbow rotation joint
* Wrist pitch, yaw, roll joints

📸 Diagram of links and joints:

```markdown
![JAKA Links & Joints](robot-mechanics/diagrams/joints-links.png)
```

📽 Mechanics demo video:

```markdown
[![Watch Mechanics Demo](robot-mechanics/demo-videos/mechanics-thumbnail.png)](https://your-mechanics-video-link.com)
```

---

## 2️⃣ Motion Commands – MoveJ, MoveL, MoveC

Robotic motion is the **heart of cobot programming**.
Here, we compare the three main commands:

### 🔹 MoveJ – Joint Movement

* Moves each joint to target angles (fastest).
* Path of tool (TCP) is not straight.
* ✅ Best for **approach, retract, repositioning**.

📽 Demo:

```markdown
[![MoveJ Demo](motion-commands/demo-videos/movej-thumb.png)](https://your-movej-video-link.com)
```

---

### 🔹 MoveL – Linear Movement

* TCP moves in a **straight line** in Cartesian space.
* Slower than MoveJ, but very precise.
* ✅ Best for **pick & place, assembly, welding**.

📽 Demo:

```markdown
[![MoveL Demo](motion-commands/demo-videos/movel-thumb.png)](https://your-movel-video-link.com)
```

---

### 🔹 MoveC – Circular Movement

* TCP follows a **circular arc** defined by two points.
* ✅ Best for **arc welding, polishing**.

📽 Demo:

```markdown
[![MoveC Demo](motion-commands/demo-videos/movec-thumb.png)](https://your-movec-video-link.com)
```

---

### 🔎 Comparison Table

| Command   | Path Type              | Speed   | Accuracy       | Use Cases                     |
| --------- | ---------------------- | ------- | -------------- | ----------------------------- |
| **MoveJ** | Joint interpolation    | Fastest | Not linear     | Approach, retract, reposition |
| **MoveL** | Linear interpolation   | Medium  | Precise linear | Pick & place, assembly        |
| **MoveC** | Circular interpolation | Medium  | Arc-precise    | Polishing, arc welding        |

---

## 3️⃣ Pick and Place – Sharpener Project

This is an **industrial pick & place task** performed with a **pneumatic gripper**.

### 🛠 Hardware Setup

* JAKA Collaborative Robot
* Pneumatic Gripper + Air Compressor
* Sharpener (target object)
* Fixtures & Work Table

📸 Setup photo:

```markdown
![Pick and Place Setup](pick-and-place/program-screenshots/setup.png)
```

---

### ⚙️ Program Flow

1. **Home Position** → Safe start
2. **Approach Position** → Move above pick object
3. **Pick** → Gripper closes (DO = On)
4. **Transfer Path** → MoveJ to place location
5. **Place** → Gripper opens (DO = Off)
6. **Retract** → Return to Home

📸 Program Flow Diagram:

```markdown
![Pick and Place Flow](pick-and-place/program-screenshots/flow.png)
```

---

### 📝 Example Code (Pseudo-JAKA Script)


MoveJ(home)
MoveJ(pre_pick)
MoveJ(pick)
SetDO(1, ON)   # Gripper close
MoveJ(retract)
MoveJ(pre_place)
MoveJ(place)
SetDO(1, OFF)  # Gripper open
MoveJ(home)
```

📽 Demo:

```markdown
[![Pick & Place Demo](pick-and-place/demo-videos/pickplace-thumb.png)](https://your-pickplace-video-link.com)
```

---

## 🦺 Safety Guidelines

* Always start with **low speed mode**
* Use **waypoints** to avoid collisions
* Adjust pneumatic pressure to prevent damage
* Keep safe zones around workspace

---

## 👩‍💻 Author

**Khushi Singh**
Project developed during Internship @ **Acrobot Technologies Pvt. Ltd.**




