# **FarmReach‑Unity — Rehabilitation Environment**  
*A real‑time Unity environment for upper‑limb rehabilitation, integrating ROS2 feedback, structured minigames, and persistent user scoring.*

## **Overview**
This repository contains the **Unity‑based rehabilitation environment** for a 2D planar robotic arm system.  
It provides:

- A gamified rehabilitation interface  
- Real‑time visualisation of user movement  
- Structured minigames targeting spatial control and endurance  
- User authentication and session management  
- Integrated scoring and feedback  

This environment forms the **interactive half** of the full rehabilitation platform.  
The ROS2 processing pipeline lives separately:

**ROS2 Rehabilitation Workspace**

---

## **System Architecture**
Unity communicates with ROS2 through the **ROS–TCP Connector**, forming a closed loop:

1. Unity reads joint‑angle data from the ESP32  
2. Unity forwards raw angles to ROS2  
3. ROS2 computes end‑effector pose + metrics  
4. Unity receives processed pose for real‑time visualisation  
5. Unity sends target angles + game events back to ROS2  

This enables low‑latency interaction aligned with human motor control.

---

## **Features**
- Real‑time movement visualisation  
- Low‑poly rehabilitation environment  
- Menu → game → results flow  
- Three minigame types (linear, rotational, endurance)  
- Unified scoring system  
- User login, registration, and persistent session tracking  
- Optional in‑game serial monitor for debugging  

---

## **Setup**

### **1. Clone the repository**
```
git clone https://github.com/el22mf/FarmReach-unity
```

### **2. Open in Unity**
- Unity **2022.3 LTS** recommended  
- Open the project folder via Unity Hub  
- Allow assets to import  

### **3. Install ROS–TCP Connector**
In Unity Package Manager:

```
https://github.com/Unity-Technologies/ROS-TCP-Connector.git
```

### **4. Configure ROS IP**
Set the ROS IP + port in:

```
Assets/Robotics/ROSSettings.asset
```

---

## **Minigames**
### **Linear Tasks**
- Reach targets  
- Follow trajectories  
- Measures accuracy + smoothness  

### **Rotational Tasks**
- Wrist rotation control  
- Angular precision scoring  

### **Endurance Tasks**
- Sustained movement  
- Fatigue‑based scoring  

---

## **User System**
- Login / Register  
- Guest mode  
- Session history  
- Automatic score logging  

Data is stored in SQLite via ROS2.

---

## **Related Repositories**
- **[FarmReach‑ROS2](https://github.com/el22mf/FarmReach-ros2)** — kinematics, metrics, data logging  

---

## **Future Work**
- Adaptive difficulty  
- Expanded minigame library  
- Improved accessibility UI  
- 3D environment upgrade  

---

# **Author**
**Matthew Foster**  
MEng Mechatronics & Robotics Engineering  
University of Leeds  
