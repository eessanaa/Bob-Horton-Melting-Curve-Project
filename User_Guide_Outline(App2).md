# 🧬 DNA Melting Curve Simulator — User Guide  
*(App 1: Nearest-Neighbor + HMM Model)*  

## 📖 Overview  
The **DNA Melting Curve Simulator** is an interactive tool that visualizes how double-stranded DNA separates (“melts”) as temperature increases.  
It uses the **SantaLucia nearest-neighbor thermodynamic model** to estimate melting temperature (Tm) and allows optional smoothing through **Hidden Markov Model (HMM)** inference.  

This simulator provides a base-by-base representation of DNA melting behavior — from duplex stability to the fraction of strands denatured — in real time.

---

## 🎯 Purpose  
This simulator helps users:
- Observe how **sequence composition**, **ionic strength**, and **strand concentration** affect melting transitions.  
- Visualize **fraction-melted curves** derived from realistic thermodynamic calculations.  
- Inspect **base-pair-level melting probability** using a colored strip visualization.  
- Understand how **nearest-neighbor stacking** contributes to DNA stability.

---

## 👥 Who It’s For  

| Audience | Goals |
|-----------|-------|
| **Students & Educators** | Learn how temperature, GC content, and ionic conditions affect DNA stability. |
| **Researchers & Biologists** | Analyze predicted melting transitions for given DNA sequences. |
| **Developers & Modelers** | Explore interactive simulation of physical-chemistry models in JavaScript. |

---

## 🚀 Getting Started  

### ✅ Requirements  
- Modern browser (Chrome, Edge, or Firefox recommended)  
- No installation — runs locally as an HTML file  

### 💡 How to Launch  
1. Download or clone the project.  
2. Open **`App1.html`** in your browser.  
3. The simulator loads automatically with a default sequence.  
4. Enter sequences and adjust parameters — curves update instantly.  

---

## 🧩 Interface Overview  

The simulator interface has **two main panels**:

| Panel | Purpose |
|--------|----------|
| **Inputs (left)** | Control DNA sequence and experimental parameters. |
| **Visualization (right)** | View melting curves and base-pair melt probabilities in real time. |

---

### 🔹 Input Panel  

| Control | Description | Default Value | Notes |
|----------|--------------|---------------|-------|
| **DNA Sequence** | Enter or paste DNA bases (A/T/G/C). | `ATGCGCATTAATCGGATGCC` | Invalid characters are ignored. |
| **Na⁺ Concentration (M)** | Sodium ion concentration affecting duplex stability. | 0.050 M | Higher Na⁺ → higher Tm (stabilization). |
| **Strand Concentration (M)** | Total DNA strand concentration for thermodynamic calculation. | 5 × 10⁻⁷ M | Impacts entropy term of Tm. |
| **Window Size (bp)** | Bases per local Tm calculation window. | 15 bp | Must be odd for symmetry. |
| **Inference Mode** | Determines smoothing method. | Independent | Options: Independent / HMM Posterior / HMM Viterbi |

---

### 🔹 Visualization Panel  

| Element | Description |
|----------|-------------|
| **Melting Curve (blue line)** | Average fraction of DNA melted across temperature. |
| **Vertical Cursor** | Moves with temperature slider to indicate the current T. |
| **Temperature Slider** | Adjusts simulation temperature (20 – 100 °C). |
| **Base-Pair Strip** | Each box = one nucleotide; color shifts blue → red as melting increases. |
| **Percent Melted Label** | Displays the fraction of bases melted at current T. |

---

## 🔄 Interactive Features  

- **Real-time updates:** All changes instantly recompute and redraw.  
- **Dynamic axis scaling:** Automatically fits curve within 20–100 °C range.  
- **Animated vertical cursor:** Smoothly follows slider movement.  
- **Color mapping:** Blue = double-stranded, Red = melted.  
- **Responsive canvas:** Resizes automatically on window resize or orientation change.

---

## 🧠 Example Walkthrough  

1. **Enter sequence:**  
   `ATGCGCATTAATCGGATGCC`  
2. **Set parameters:**  
   - Na⁺ = 0.05 M  
   - Strand conc = 5 × 10⁻⁷ M  
   - Window = 15 bp  
   - Inference = Independent  
3. **Slide temperature** from 20 °C → 100 °C.  
4. **Observe:**  
   - Fraction melted rises near 65 °C.  
   - Base-pair strip changes from blue → red.  
   - “Percent melted” ≈ 50 % around Tm.  

---

## 🧩 Interpreting Results  

| Factor | Effect on Tm | Physical Meaning |
|---------|---------------|-----------------|
| **↑ GC content** | Increases Tm | GC pairs have 3 H-bonds vs 2 in AT. |
| **↑ Sequence length** | Increases Tm | More base-pair interactions. |
| **↑ Na⁺ concentration** | Increases Tm | Ionic shielding reduces repulsion. |
| **↑ A/T ratio** | Decreases Tm | Weaker hydrogen bonding. |

---

## 🧮 Thermodynamic Basis  

Melting temperatures are derived from nearest-neighbor ΔH and ΔS parameters (SantaLucia 1998).  
Each dinucleotide contributes enthalpy (ΔH) and entropy (ΔS) terms summed across the sequence.  

Formula:  

\`\`\`text
Tm (°C) = (ΔH × 1000) / (ΔS + R ln(Ct / 4)) – 273.15 + 16.6 log₁₀[Na⁺]
\`\`\`

where R is the gas constant and Ct is strand concentration.  
*(HMM modes smooth probabilities but don’t change thermodynamic values.)*

---

## 📊 Tips & Best Practices  

- Use 20 – 200 bp sequences for clear curves.  
- Avoid extreme ion levels (< 0.001 M or > 1 M).  
- Smaller window = local fluctuations; larger window = smoother curve.  
- Temperature increments of 0.5 °C give a good balance between speed and detail.  

---

## 🧱 Planned Improvements  

| Feature | Description |
|----------|-------------|
| 🧮 Multi-sequence comparison | Overlay curves for two DNA samples. |
| 🧫 Salt effect demo | Compare Na⁺ vs Mg²⁺ effects on Tm. |
| 💾 Export tools | Save curves as CSV or PNG. |
| 🎓 Teaching modes | Preset lesson scenarios for classrooms. |

---

## 🧩 Summary  

The **DNA Melting Curve Simulator** provides a clear, interactive visualization of how DNA duplexes denature with temperature.  
By adjusting parameters like salt concentration and sequence length, users gain hands-on insight into the biophysical principles of DNA stability.  

Ideal for **teaching, analysis, and demonstration** in molecular biology, bioinformatics, and biotechnology labs.

---

**Created for educational and research use — bridging DNA thermodynamics and interactive visual learning.**
