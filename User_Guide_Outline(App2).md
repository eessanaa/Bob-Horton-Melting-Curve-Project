# 🧬 DNA Melting Curve Simulator — User Guide

## Introduction
- **Purpose:**  
  The DNA Melting Curve Simulator allows users to visualize and understand how DNA strands separate (melt) as temperature increases.  
  It connects fundamental **DNA thermodynamics** to the **melting curve analysis** commonly used in qPCR and other molecular biology applications.

- **Audience:**  
  - **Molecular Biologists:** interpret melting curves and temperature transitions.  
  - **Programmers:** understand the algorithmic model (nearest-neighbor thermodynamics + HMM).  
  - **Students & Teachers:** explore the relationship between sequence composition and DNA stability.

---

## Getting Started
- **System Requirements:**  
  A modern web browser such as Chrome, Edge, or Firefox.

- **How to Launch:**  
  1. Open the file `Week_4_App2_DNA_Melting_Curve.html` in your browser.  
  2. The simulator interface will appear with adjustable input fields and a live chart.

- **Interface Overview:**  
  - Input boxes for DNA sequence and parameters.  
  - Plot area showing the *Fraction Melted* (red) and *Derivative* (blue).  
  - Results update automatically whenever you change inputs.

<img width="1400" height="858" alt="image" src="https://github.com/user-attachments/assets/632e7d7a-2e9f-4366-8083-ca8d2c2a4beb" />

---

## Understanding the Interface
The simulator interface is divided into three main parts: **Input Panel**, **Parameter Controls**, and **Plot Display**.  
Each component serves a specific purpose to help users visualize melting behavior interactively.

---

### 1️⃣ Input Panel (Top Section)
- **DNA Sequence Box:**  
  Located near the top of the app. Enter any DNA sequence using the characters A, T, G, and C.  
  - Example: `ATGCGCGTTAGC`  
  - The program automatically ignores lowercase letters or spaces.  
  - After entering the sequence, the melting curve updates instantly (no need to press a “Run” button).

---

### 2️⃣ Parameter Controls (Middle Section)
Directly below the sequence box are the controls for experimental conditions. These parameters affect how the DNA melts.

- **Na⁺ concentration (M):**  
  Adjusts sodium ion concentration.  
  - Higher Na⁺ → more stable helix → higher Tm.

- **Mg²⁺ concentration (M):**  
  Strongly influences duplex stability.  
  - Typically set to 0.005 M by default.  
  - Increasing Mg²⁺ shifts the melting curve right (higher Tm).

- **Temperature Range:**  
  - **Start Temp (°C):** Beginning of the simulation (default 40 °C).  
  - **End Temp (°C):** End of the simulation (default 95 °C).  
  - **Step (°C):** Temperature increment (smaller = smoother curve).  

---

### 3️⃣ Output Plot (Bottom Section)
This section visualizes the DNA melting process using two real-time curves.

- **Red Curve — Fraction Melted:**  
  Displays the proportion of DNA that is single-stranded at each temperature.  
  - Y-axis (left) = fraction melted (0 = fully double-stranded, 1 = fully melted).  
  - The S-shaped region marks the melting transition.

- **Blue Curve — Derivative (dFraction/dT):**  
  Represents the rate of melting with temperature.  
  - Y-axis (right).  
  - The **peak corresponds to the melting temperature (Tm)** — the point of fastest strand separation.

> 💡 Hover over any point to display exact temperature and melting fraction values.

---

### 4️⃣ Interactive Behavior
- All changes update the plots in real time.  
- The app uses a **Hidden Markov Model (HMM)** to smooth transitions between melted and bound regions.  
- Chart.js automatically rescales the axes to fit the melting region.  
- Adjusting Na⁺, Mg²⁺, or sequence instantly recalculates the entire curve.

---

### 5️⃣ Example Walkthrough
1. Enter the sequence `ATGCGCGTTAGC`.  
2. Keep Na⁺ = 0.05 M, Mg²⁺ = 0.005 M, Start = 40 °C, End = 95 °C, Step = 1 °C.  
3. Observe:
   - Fraction Melted (red) rises sharply near 80–90 °C.  
   - Derivative (blue) peaks around 88 °C → **Tm ≈ 88 °C**.

---

## Understanding the Parameters
Each parameter affects the DNA duplex stability differently:

- **Sequence Composition:**  
  More G–C pairs = more hydrogen bonds = higher Tm.  
  A–T pairs have fewer hydrogen bonds and melt earlier.

- **Ion Concentration:**  
  Ions stabilize the negatively charged phosphate backbone.  
  Higher Na⁺ or Mg²⁺ = stronger helix = higher Tm.

- **Temperature Range:**  
  Defines the range for the simulation.  
  Smaller step values produce smoother, more detailed transitions.

---

## Output Graphs
### 🔴 Fraction Melted (Red)
- Displays the proportion of DNA that is single-stranded at each temperature.  
- The S-shaped rise marks the transition region.  
- Y-axis (left) = fraction melted, X-axis = temperature.

### 🔵 Derivative d(Fraction)/dT (Blue)
- Shows the rate of melting vs. temperature.  
- The peak identifies the **melting temperature (Tm)** — the point of fastest strand separation.  
