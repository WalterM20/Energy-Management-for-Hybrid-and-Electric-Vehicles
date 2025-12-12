# Hybrid Electric Vehicle Energy Management Strategies (EMS)

## 📌 Project Overview
This repository contains the development and simulation of various Energy Management Strategies for a parallel Hybrid Electric Vehicle (HEV). The goal was to minimize fuel consumption while maintaining charge-sustaining behavior and preserving battery health (SOH).

## 🛠️ Methodologies Implemented
The project explores four distinct control strategies, evolving in complexity and efficiency:

1.  **Thermostat Control (Rule-Based):** A heuristic strategy that switches the Internal Combustion Engine (ICE) on/off based on State of Charge (SOC) thresholds.
    * *Result:* Baseline fuel consumption established.
2.  **ECMS (Equivalent Consumption Minimization Strategy):** A local optimization strategy that converts electrical energy usage into equivalent fuel cost.
    * *Key Feature:* Calibration of the equivalence factor ($s$) using a bisection algorithm.
3.  **A-ECMS (Adaptive ECMS):** An on-the-fly adaptation of the equivalence factor based on driving conditions and SOC feedback, making the controller robust to unknown driving cycles.
    * *Calibration:* Tuning of the proportional gain ($K_p$) for optimal SOC tracking.
4.  **Dynamic Programming (Global Optimization):** Implementation of a backward-facing algorithm to find the absolute global optimum for a specific drive cycle.
    * *Focus:* Analyzed the trade-off between Fuel Economy and Battery Aging by varying the weighting factor ($\alpha$).

## 💻 Tech Stack
* **Software:** MATLAB
* **Techniques:** Optimal Control, Bisection Algorithm, Backward/Forward-facing Models.
* **Drive Cycles Tested:** WLTP, Artemis Motorway (AMDC), Artemis Urban (AUDC), Turin Test Cycle.

## 📊 Key Results
* **Fuel Economy:** The Dynamic Programming approach demonstrated the theoretical lower bound for fuel consumption ($ \approx 3.79 l/100km$ on ARDC).
* **Battery Aging:** Introduced an aging-aware cost function in the DP algorithm, achieving a 50% increase in estimated battery life with negligible fuel penalty.
* **Real-time feasibility:** The A-ECMS proved to be the most viable solution for real-time implementation, offering near-optimal results with low computational cost.
