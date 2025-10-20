# DNA Melting Curve Simulator — User Guide Outline

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
  1. Open the file in your browser.  
  2. The simulator interface will appear with adjustable input fields and a live chart.

- **Interface Overview:**  
  - Input boxes for DNA sequence and parameters.  
  - Plot area showing the *Fraction Melted* (red) and *Derivative* (blue).  
  - Results update automatically whenever you change inputs.

<img width="1400" height="858" alt="image" src="https://github.com/user-attachments/assets/632e7d7a-2e9f-4366-8083-ca8d2c2a4beb" />

---

## Inputs
### DNA Sequence
- Enter any DNA sequence composed of A, T, G, and C.  
- Example: `ATGCGCGTTAGC`  
- Case-insensitive and spaces are ignored.

### Ionic Conditions
- **Na⁺ concentration (M):** Controls stability of the double helix.  
  - Higher Na⁺ → stronger helix → higher Tm.  
- **Mg²⁺ concentration (M):** Has a similar but stronger stabilizing effect.

### Temperature Range
- **Start Temp (°C):** Lowest temperature in the simulation (default: 40).  
- **End Temp (°C):** Highest temperature (default: 95).  
- **Step (°C):** Increment between data points (smaller step = smoother curve).

---

## Output Graphs
### 🔴 Fraction Melted (Red)
- Displays the proportion of DNA that is single-stranded at each temperature.  
- The S-shaped rise marks the transition region.  
- Y-axis (left) = fraction melted, X-axis = temperature.

### 🔵 Derivative d(Fraction)/dT (Blue)
- Shows the rate of melting vs. temperature.  
- The peak identifies the **melting temperature (Tm)** — the point of fastest strand separation.  
- Y-axis (right) = derivative, X-axis = temperature.

---

## Interpreting Results
- **GC-rich sequences** have higher melting points than **AT-rich** sequences.  
- **Higher salt** concentrations shift curves to the right (more stable DNA).  
- **Broad peaks** suggest mixed sequence stability or multi-domain melting.  
- The **derivative peak temperature** is the experimental equivalent of Tm.

---

## How It Works (For Programmers)
- Uses **nearest-neighbor thermodynamic parameters** to calculate ΔH and ΔS for each dinucleotide.  
- Converts these into ΔG = ΔH – TΔS to estimate strand stability at each temperature.  
- Applies a **Hidden Markov Model (HMM)** to smooth transitions between melted and bound regions.  
- Plots data in real time using **Chart.js**.

---

## Example Workflow
1. Enter sequence: `ATGCGCGTTAGC`  
2. Set:
   - Na⁺ = 0.05 M  
   - Mg²⁺ = 0.005 M  
   - Start = 40 °C, End = 95 °C, Step = 1 °C  
3. Observe:
   - Fraction melted curve rises near 80–90 °C.  
   - Derivative curve peaks around 88 °C → approximate Tm.

---

## Tips for Use
- Try sequences with different **GC contents** to see how Tm changes.  
- Reduce **Step** size (e.g., 0.5 °C) for smoother data.  
- Compare results with **uMelt** or **Wallace equation** for validation.  
- Use this tool to demonstrate how **sequence composition** and **ionic strength** influence DNA melting.

---

## Future Additions (Optional)
- Add export to CSV or PNG.  
- Display single-number Tm on the interface.  
- Integrate Wallace rule or uMelt comparison directly into the app.  

---



