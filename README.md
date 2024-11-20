# Orbital Elements and Numerical Solution to Kepler's Equation

## Overview

This project calculates the **position** and **velocity** of a satellite orbiting Earth, 4 hours after passing the periapsis, using Kepler's laws and orbital mechanics. It walks through the steps to solve Kepler's Equation numerically and compute orbital parameters step by step. 

---

### **Problem Statement**
Determine the position (distance from Earth) and velocity of a satellite at a given time after crossing the periapsis. The problem starts with given orbital elements and involves solving equations for Mean Anomaly, Eccentric Anomaly, True Anomaly, and finally deriving the satellite's position and velocity.

---

## **Inputs**
- **Semi-Major Axis** (\(a\)): \(25,512 \, \text{km}\)
- **Eccentricity** (\(e\)): \(0.625\)
- **Time Since Periapsis** (\(t\)): \(4 \, \text{hours}\)
- Initial True Anomaly: \(f(0) = 0 \, \text{rad}\)

---

## **Equations and Solution Workflow**

The following steps solve the problem:
  
### 1. **Mean Anomaly** (\(M\))  
\[
M(t) = n \cdot t \quad \text{where} \quad n = \sqrt{\frac{\mu}{a^3}}
\]
Here, \(n\) is the average angular speed of the satellite, and \(\mu = GM\) is the gravitational parameter.

### 2. **Eccentric Anomaly** (\(E\))  
Solve **Kepler's Equation** numerically using Newton-Raphson:
\[
M = E - e \cdot \sin(E)
\]

### 3. **True Anomaly** (\(f\))  
\[
\tan\left(\frac{f}{2}\right) = \sqrt{\frac{1 + e}{1 - e}} \cdot \tan\left(\frac{E}{2}\right)
\]

### 4. **Position (r)**  
\[
r(t) = \frac{a \cdot (1 - e^2)}{1 + e \cdot \cos(f(t))}
\]

### 5. **Velocity (v)**  
Using the **Vis Viva Equation**:
\[
v = \sqrt{\mu \left(\frac{2}{r} - \frac{1}{a}\right)}
\]

---

## **Results**
1. **Mean Anomaly (\(M\))**:
   - \(\mathbf{M = 2.94 \, \text{rad}}\)

2. **Eccentric Anomaly (\(E\))**:
   - Solved numerically: \(\mathbf{E = 2.861 \, \text{rad}}\)

3. **True Anomaly (\(f\))**:
   - \(\mathbf{f = 2.861 \, \text{rad}}\)  
   - Converted to degrees: \( \mathbf{f \approx 163.98^\circ}\)

4. **Position (\(r\))**:
   - Distance from Earth: \(\mathbf{r = 18,797 \, \text{km}}\)

5. **Velocity (\(v\))**:
   - Velocity: \(\mathbf{v = 6.293 \, \text{km/s}}\)

---

## **Code Implementation**

The solution uses Python for computation. Key components include:
- **Newton-Raphson Method**: Iteratively solve Kepler's Equation for \(E\).
- Libraries used: `numpy` for numerical calculations.
- Each step outputs intermediate results for better understanding.

---

## **How to Run**
1. **Prerequisites**: Python installed with the `numpy` library.
2. **Execute the Code**: Run the provided Python script to compute the results step-by-step.

---

## **Conclusions**
After 4 hours since crossing the periapsis, the satellite will be:
- At a distance of **18,797 km** from Earth.
- Moving with a velocity of **6.293 km/s**.

This computation demonstrates how to predict satellite motion using orbital mechanics and Kepler's laws.