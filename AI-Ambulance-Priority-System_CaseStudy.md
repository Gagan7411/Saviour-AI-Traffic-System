# 🚨 AI-Powered Ambulance Priority Prediction System  
*Research Case Study | Add-on to Bengaluru Adaptive Traffic Control System (BATCS)*  

---

## 🧩 Overview  

This research focuses on an **AI-powered add-on module** for the **Bengaluru Adaptive Traffic Control System (BATCS)** that enhances its ability to handle **emergency vehicle prioritization**, specifically **ambulances**.  

Unlike traditional signal systems that react when an ambulance reaches the intersection, this model **predicts and pre-optimizes** the route **up to 2 km in advance**, ensuring a smooth passage even during high traffic density or when multiple ambulances are in operation.

---

## 🚑 Problem Statement  

Urban areas often face delays in emergency response due to:  
- Congested intersections with delayed manual or sensor-triggered signal response.  
- No coordination between multiple intersections or approaching ambulances.  
- Lack of predictive route adjustment based on real-time distance and direction.  

The goal is to **integrate AI-based predictive control** into BATCS to reduce these delays and automate priority decisions.

---

## ⚙️ Proposed System  

### 🔹 Core Idea  
The system leverages **AI, IoT, and GPS-based sensor networks** to identify approaching ambulances, **predict their arrival distance**, and **manage traffic signals dynamically**.  

When an ambulance is detected within a 2 km radius, the AI predicts:  
- Its **arrival time**,  
- **Route direction**,  
- **Current speed**, and  
- **Nearest signal points** that must turn green in sequence.

---

## 🧠 How the AI Prediction Works  

1. **Data Input:**  
   - IoT roadside sensors detect vehicle siren or light patterns.  
   - GPS module from the ambulance sends live coordinates and speed.  
   - Traffic density data is fetched from existing BATCS sensors.  

2. **AI Processing:**  
   - A prediction model estimates **ETA (Expected Time of Arrival)** using real-time speed and distance.  
   - Checks for **road congestion levels** and re-prioritizes nearby signals.  
   - Uses **priority ranking** when more than one ambulance is detected.  

3. **Output Decision:**  
   - Updates signal controllers to open a **“Green Corridor”** path.  
   - Displays live updates in the control center dashboard.  
   - Reverts signals back to adaptive mode after ambulance clearance.

---

## 🔄 Dual Ambulance Management  

When **two ambulances** approach from opposite sides:  
- The AI calculates **Priority Weightage** based on:  
  - Distance to the intersection  
  - Patient severity (if data available)  
  - Available diversion routes  
- Temporarily adjusts signals and sets **alternate corridor paths** to avoid deadlocks.  

If one ambulance turns right/left, nearby IoT sensors and directional meters update the AI in milliseconds, allowing **instant rerouting** and **signal re-sequencing**.

---

## 🧭 System Architecture  

```text
[Ambulance GPS & Sensors] 
        ↓
 [Data Gateway (IoT Hub)]
        ↓
 [AI Prediction Engine]
        ↓
 [Traffic Signal Control Module] 
        ↓
 [Smart Traffic Junctions + BATCS Integration]
```

### Key Components  
- **IoT Sensors:** Detect ambulance siren, beacon light, and distance.  
- **AI Engine:** Predicts path and ETA using distance–speed calculations.  
- **Signal Control Unit:** Executes light sequencing logic.  
- **Cloud Dashboard:** Visual monitoring and manual override (if required).  

---

## 🧮 Algorithm Logic  

### Step-by-Step Process  

1. Detect ambulance presence (via sound, GPS, or visual feed).  
2. Measure distance between ambulance and nearest signal.  
3. Predict time-to-arrival using:  
   \[
   ETA = \frac{Distance}{Speed}
   \]
4. Compare against threshold (e.g., 2 km radius).  
5. Identify affected intersections along the route.  
6. Assign **priority index** for each intersection based on ETA and congestion.  
7. Adjust signals dynamically:  
   - Green = route corridor  
   - Red = cross-flow halt  
8. Update every 5 seconds using sensor feedback.  
9. Once ambulance clears zone → revert to normal adaptive mode.  

---

## 🧰 Technology Stack  

| Layer | Tools / Frameworks |
|-------|--------------------|
| **AI & ML** | Python, TensorFlow, Scikit-learn |
| **IoT & Communication** | Arduino/Raspberry Pi, Ultrasonic sensors, GSM/GPS module |
| **Backend** | Node.js, Express.js |
| **Data Storage** | MongoDB / Firebase |
| **Visualization** | Web dashboard (React / Chart.js) |
| **Integration** | REST APIs with BATCS & City Control Hub |

---

## 📊 Data Flow Diagram  

![System Flow Diagram](diagram.png)  
*Illustration of communication between ambulance, sensors, AI model, and signal controllers.*

---

## 🚀 Expected Outcome  

| Parameter | Traditional System | AI Prediction Add-on |
|------------|-------------------|----------------------|
| Ambulance Delay | 3–5 mins | < 1 min |
| Detection Range | < 300 m | Up to 2 km |
| Dual Ambulance Handling | No | Yes |
| Dynamic Rerouting | No | Yes |
| Learning Capability | No | Continuous ML Improvement |

---

## 📈 Impact  

- Reduces **ambulance arrival time** by up to **60%**.  
- Minimizes manual signal intervention.  
- Enables **data-driven decisions** for emergency management.  
- Strengthens **smart city infrastructure** through AI automation.  

---

## 🔮 Future Enhancements  

- Integrate **5G IoT sensors** for ultra-low-latency communication.  
- Add **priority tagging** via hospital input (critical vs. non-critical).  
- Include **drone-assisted traffic mapping** for real-time visualization.  
- Combine with **Emergency AI Watch** for predictive medical alerts and automatic dispatch.  

---

## 📚 References  

- Bengaluru Traffic Management Centre (BTMC) documentation on BATCS.  
- IEEE Research Papers on AI-driven traffic optimization.  
- Open-source projects on Intelligent Transportation Systems (ITS).  

---

**Author:** Gagan M  
**Institution:** MLA Academy of Higher Learning  
**Category:** Research & AI System Design  
**GitHub Repo:** [AI-Ambulance-Priority-System](https://github.com/YourUsername/AI-Ambulance-Priority-System)  
**License:** MIT  
