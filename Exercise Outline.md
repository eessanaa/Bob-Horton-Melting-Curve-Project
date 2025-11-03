# DNA Melting Teaching App — Exercise Outline

## Purpose
The goal of this app is to create an **interactive, configurable simulation environment** for teaching DNA melting behavior.  
It will allow instructors and students to visualize how DNA strands denature with temperature and explore how sequence composition or environmental factors affect melting temperature (Tm).

---

## Overview
The app will have **multiple selectable modes**, each focusing on a different concept of DNA melting.  
All modes will share the same visualization interface but can be customized for different experiments or demonstrations.

The app will:
- Plot **melting curves** showing the fraction of double-stranded DNA versus temperature.  
- Display **first derivative plots (dF/dT)** to identify the apparent melting temperature (Tmₐₚₚ).  
- Allow comparisons between sequences (e.g., reference vs variant).  
- Enable users to modify parameters like **GC%**, **sequence length**, and **salt concentration**.  
- Export results for educational or analysis purposes.

---

## Key Features (Configurable)
- **Sequence Settings:** adjustable GC%, length, and number of sequences.  
- **Chemical Environment:** control Na⁺ and Mg²⁺ concentration.  
- **Visualization Options:** toggle derivative curve, difference curves, and multiple overlays.  
- **Configurable Modes:** Basics, Disease Variant Identification, Dataset Generation, Salt Dependence.  
- **Outputs:** interactive plots, downloadable datasets, and images for lab exercises.

---

## Educational Modes

### 🧩 Mode A: Basics
**Goal:** Teach the fundamentals of DNA melting behavior.  
Students will observe how double-stranded DNA separates into single strands as temperature increases.

**Example activity:**
- Generate a 100-base sequence with 40% GC content and visualize its melting curve.  
- Compare to a 60% GC sequence and discuss why its Tm is higher (more hydrogen bonds = higher stability).  
- Observe how increasing sequence length sharpens the melting transition.

---

### 🧬 Mode B: Disease Variant Identification
**Goal:** Compare melting curves of different DNA strands to simulate how mutations or viral variants affect stability.  
Students will visualize how small sequence changes alter the melting temperature or the derivative peak.  

**Examples:**
- **SARS-CoV-2:** Compare Wuhan-Hu-1 and Omicron BA.1 spike gene fragments (~100 bases, 40% GC).  
  - Observation: Minor base substitutions slightly reduce Tm (less stable duplex).  
- **Influenza A:** Compare HA fragments from the California/2009 and Michigan/2015 strains (~100 bases, 45–50% GC).  
  - Observation: Slightly higher GC% in the Michigan variant increases Tm (greater stability).  

Students will analyze which variant has the higher Tm and explain what this means for hybridization strength and diagnostic sensitivity (e.g., RT-PCR mismatches).

---

### 📊 Mode C: Dataset Generation
**Goal:** Automatically create a set of synthetic DNA sequences and their melting data for computational or ML use.  
Students will explore trends across GC%, length, and salt conditions.

**Example setup:**
- Generate 200 total sequences.  
- GC% range: 30–70%.  
- Length range: 80–160 bases.  
- Na⁺ concentration range: 10–150 mM.  
- Output: table or dataset linking sequence parameters to predicted Tm values.  

---

### 💧 Mode D: Salt Dependence
**Goal:** Show how ionic strength influences DNA duplex stability.  
Students will observe how increasing salt concentration raises Tm by screening electrostatic repulsion.

**Example setup:**
- 100-base sequence with 40% GC content.  
- Compare salt levels: 10 mM, 50 mM, 100 mM, 150 mM Na⁺.  
- Observation: Higher salt concentrations increase Tm due to reduced charge repulsion between strands.  

---

## Educational Outcomes
By completing this exercise, students will:
- Interpret melting and derivative curves.  
- Understand how GC%, sequence length, and salt concentration influence Tm.  
- Recognize how single mutations can affect duplex stability.  
- Connect these molecular changes to real-world applications like **disease variant detection** and **PCR assay design**.

---

## Deliverables
For each mode, students will submit:
- Screenshots or images of their plotted curves.  
- A short paragraph summarizing their observations.  
- A small results table showing GC%, length, salt concentration, and measured Tm.  
- A brief conclusion connecting the observed results to thermodynamic principles.

---

## Instructor Summary
> This teaching app introduces students to DNA melting and thermodynamic stability through configurable simulations.  
> Each mode provides a distinct educational angle — from visualizing basic melting behavior to comparing real viral variants or testing ionic strength effects.  
> The interactive format supports both guided instruction and independent exploration.

---

## Next Steps (Implement)
In the next phase, we will:
- Build the **interactive app interface** (Connect to the app).  
- Develop the **configuration system**, allowing instructors to switch between modes and input custom parameters.  
- Incorporate **data export options** (e.g., CSV, PNG) for student answers.  
- Test the app with example sequences from Mode B to ensure the plots and derivative curves behave as expected. --> To ensure correct plots, use UMelt.  
