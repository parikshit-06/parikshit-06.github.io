---

layout: post
title: "GestureNav: Controlling Drones with Hand Gestures Using MediaPipe + ROS2"
date: 2025-07-04
categories: \[blog, project]
projects: true
--------------

GestureNav is my attempt at building a natural interface for drone navigation using **bare hands** — no gloves, no controllers. Just gestures, computer vision, and a drone that listens.

In this post, I’ll walk through how I connected **MediaPipe**, **ROS2**, and **PX4** to fly a drone using real-time hand signals.

## 🎯 Why Gesture Control?

Traditional RC controllers are great, but:

* Not intuitive for non-experts
* Require both hands and active focus
* Not viable in certain field conditions

Gesture control offers an expressive, intuitive, and low-friction alternative — especially for search & rescue or inspection missions.

## 🧠 The Pipeline

**MediaPipe Hands** gives you 21 3D landmarks per hand at 30+ FPS. We use this to detect gestures like:

### System Stack:

* **MediaPipe** (gesture detection)
* **ROS2** (bridge & logic layer)
* **PX4 SITL** or real drone (control interface)

I trained a simple gesture classifier and mapped outputs to velocity commands.

## ⚙️ ROS2 Integration

Each gesture becomes a custom ROS2 message:

```bash
/gesture_nav/command -> geometry_msgs/Twist
```

A ROS2 node interprets gestures and publishes motion commands to the drone via MAVROS.

Example:

```python
if gesture == 'thumb_up':
    twist.linear.z = 0.5
elif gesture == 'point_left':
    twist.linear.y = 0.3
```

## 🚁 Testing with PX4 SITL

I first validated the system in **PX4 Gazebo SITL**, simulating commands with fake camera input. Then, field-tested with a real quadcopter using **Jetson Nano + USB webcam**.

Latency was \~100ms end-to-end — usable for smooth, slow motion.

## 🔥 Challenges

* MediaPipe's hand detection breaks at distance/light variance
* Gesture misclassifications in dynamic backgrounds
* Needed deadzones and confidence thresholds

## 🌟 What’s Next

* Add support for **dynamic gestures** (swipes, sequences)
* Improve robustness under occlusion and glare
* Try integrating with **voice commands**

---

GestureNav is open-source and actively evolving. If you want to try it out or contribute, [check the repo](https://github.com/parikshit-06)!
