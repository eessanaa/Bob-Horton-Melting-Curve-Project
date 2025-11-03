# 🧬 DNA Melting Curve Simulator — User Guide

## 📖 Overview
The **DNA Melting Curve Simulator** is an interactive educational tool that demonstrates how DNA strands separate (“melt”) as temperature increases.  
It links the thermodynamics of DNA duplex stability to **melting curve analysis**, a technique widely used in qPCR and molecular diagnostics.

### 🎯 Purpose
This simulator helps users:
- Visualize DNA melting curves and understand how **GC content**, **ion concentration**, and **sequence length** affect melting temperature (Tm).  
- Explore **real-time curve generation** using biologically realistic thermodynamic models.  
- Interpret **fraction melted** and **derivative (dF/dT)** plots as they relate to DNA stability and hybridization efficiency.

### 👥 Who It’s For
| Audience | Goals |
|-----------|-------|
| **Students & Teachers** | Learn the relationship between DNA composition, salt concentration, and Tm. |
| **Molecular Biologists** | Analyze melting transitions and interpret experimental melting behavior. |
| **Programmers & Developers** | Understand how thermodynamic parameters and visualization models can be implemented in a web app. |

---

## 🚀 Getting Started

### ✅ Requirements
- A modern web browser (Chrome, Edge, or Firefox recommended)
- No installation or additional software needed

### 💡 How to Launch
1. Open the `index.html` file in your browser.  
2. The simulator will load with default settings.  
3. You can immediately begin entering sequences and adjusting parameters.  
4. The melting curves update automatically — no “Run” button required.

---

## 🧩 Interface Overview

The simulator is divided into **three main panels**:

| Section | Purpose |
|----------|----------|
| **1️⃣ Input Panel** | Enter or paste DNA sequences (A, T, G, C). |
| **2️⃣ Parameter Controls** | Adjust environmental and experimental conditions. |
| **3️⃣ Plot Display** | View melting and derivative curves in real time. |

---

### 1️⃣ Input Panel
- Enter your DNA sequence using A, T, G, and C.  
  Example: `ATGCGCGTTAGC`  
- The simulator automatically filters invalid characters and updates instantly.  
- Lowercase letters, spaces, and invalid symbols are ignored.

---

### 2️⃣ Parameter Controls
Modify the key experimental conditions to see their effects on melting behavior:

| Parameter | Description | Default | Effect |
|------------|--------------|----------|---------|
| **Na⁺ concentration (M)** | Adjusts sodium ion levels | 0.05 | Higher Na⁺ = higher Tm |
| **Mg²⁺ concentration (M)** | Controls magnesium ion levels | 0.005 | Strong stabilizing effect |
| **Start Temperature (°C)** | Beginning of the simulation | 40 | Defines lower bound of plot |
| **End Temperature (°C)** | Upper limit of simulation | 95 | Defines upper bound of plot |
| **Step Size (°C)** | Temperature increments | 1 | Smaller step = smoother curve |

---

### 3️⃣ Plot Display
The plot area dynamically shows how DNA melts under chosen conditions.

#### 🔴 Fraction Melted (Red Curve)
- Represents the proportion of DNA that has melted at each temperature.  
- Y-axis (left): fraction melted (0 = fully double-stranded, 1 = fully melted).  
- The **S-shaped curve** marks the transition region between dsDNA and ssDNA.

#### 🔵 Derivative Curve (Blue)
- Displays the rate of melting (dFraction/dT).  
- Y-axis (right): rate of melting.  
- The **peak** of the blue curve corresponds to **Tm**, the apparent melting temperature.

> 💡 Tip: Hover over the plot to see temperature and fraction values at any point.

---

## 🔄 Interactive Features

- **Live updates:** All changes to sequence or parameters automatically refresh both curves.  
- **Dynamic scaling:** The chart automatically adjusts axis limits to center around the melting region.  
- **Realistic modeling:** Uses a **nearest-neighbor thermodynamics approach** to estimate stability and simulate melting transitions.  
- **Smooth transitions:** A Hidden Markov Model (HMM) framework ensures smooth melting region boundaries.

---

## 🧠 Example Walkthrough

1. **Enter sequence:**  
   `ATGCGCGTTAGC`  
2. **Set parameters:**  
   - Na⁺ = 0.05 M  
   - Mg²⁺ = 0.005 M  
   - Start = 40 °C  
   - End = 95 °C  
   - Step = 1 °C  
3. **Observe:**  
   - The red fraction-melted curve increases sharply between 80–90 °C.  
   - The blue derivative curve peaks around 88 °C.  
   - Therefore, **Tm ≈ 88 °C**, meaning half of the DNA duplexes are separated at this temperature.

---

## 🧩 Interpreting Results

| Parameter | Effect on Tm | Explanation |
|------------|---------------|-------------|
| **Higher GC content** | ↑ Tm | More hydrogen bonds per base pair |
| **Longer sequences** | ↑ Tm | More cumulative base pairing interactions |
| **Higher Na⁺/Mg²⁺** | ↑ Tm | Ionic shielding reduces repulsion between strands |
| **More A–T pairs** | ↓ Tm | Weaker hydrogen bonding reduces stability |

---

## 📊 Output and Analysis

The simulator provides **two key outputs**:

1. **Fraction Melted Curve (Red)**  
   - Shows the overall DNA melting transition.  
   - The slope indicates how cooperative the melting process is.

2. **Derivative Curve (Blue)**  
   - Highlights the melting temperature (Tm) as a distinct peak.  
   - Multiple peaks may indicate heterogeneous regions or secondary structures.

Both graphs can be exported or screenshotted for lab reports and educational exercises.

---

## 🧾 Example Use Cases

| Mode | Description |
|------|--------------|
| **Educational Demonstration** | Show students how GC%, salt, and sequence length affect melting. |
| **Variant Comparison** | Compare melting profiles between disease variants (e.g., SARS-CoV-2 strains). |
| **Parameter Testing** | Explore how changing Na⁺ or Mg²⁺ concentration shifts the Tm curve. |
| **Data Generation** | Produce simulated datasets for machine learning or statistical modeling. |

---

## 🧭 Tips & Best Practices
- Keep sequences between **20–200 bases** for smooth curves.  
- Avoid extremely low or high ion concentrations that may cause unrealistic melting behavior.  
- Use a **temperature step** of 0.5–1.0 °C for optimal balance between speed and curve detail.  
- Always check that your derivative peak aligns with the expected biological range.

---

## 🧱 Next Steps (Development Roadmap)
Planned future features include:
- 🧮 Configurable “Teaching Modes” (Basics, Variant ID, Dataset, Salt Dependence)  
- 💾 Exportable datasets (CSV, PNG)  
- ⚙️ JSON-based instructor configuration for automated lesson setup  
- 🧫 Example sequence library for real-world variant demonstrations  

---

## 🧩 Summary
The **DNA Melting Curve Simulator** offers an interactive way to connect DNA thermodynamics, base composition, and environmental effects to visual melting behavior.  
Whether used for teaching, analysis, or modeling, it provides a clear and intuitive view of how DNA duplexes respond to changing temperature and ionic strength.

---

**Created for educational and research purposes — ideal for molecular biology, bioinformatics, and biotechnology teaching labs.**
