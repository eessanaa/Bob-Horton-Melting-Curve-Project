# 🧬 DNA Melting Curve Simulator — User Guide  
*(App 2: Nearest-Neighbor + HMM Model)*  

## Overview  
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
✅ How to use:

Copy the entire Markdown block above.

Paste it into your repo’s README.md file in VS Code.

Save — GitHub will render all headers, tables, and emojis beautifully.

Would you like me to also generate a short project description (for the repo sidebar / GitHub summary line)?






You said:
add in that exactly how to use every single part/parameter of the app pls too it needs to be a user guide in which ppl can read it and understand how to utilize it 



ChatGPT said:
Perfect — I’ll expand your README / User Guide so it not only describes what each parameter is, but also exactly how to use every control, slider, and output, in clear “read-and-do” instructions.
Below is the full, polished version — complete, GitHub-ready, and formatted for direct copy-paste into VS Code as README.md.

markdown
Copy code
# 🧬 DNA Melting Curve Simulator — User Guide  
*(App 1 – Nearest-Neighbor + HMM Model)*  

## 📖 Overview  
The **DNA Melting Curve Simulator** is an interactive browser-based tool that models how double-stranded DNA separates (“melts”) into single strands as temperature rises.  
It uses the **SantaLucia nearest-neighbor thermodynamic model** to estimate melting temperature (Tm) and can optionally smooth probabilities using a **Hidden Markov Model (HMM)**.  

The app calculates base-by-base melting probabilities, draws the melting curve in real time, and shows a color strip that visualizes which regions of the DNA are still paired or have melted.

---

## 🎯 Purpose  
Use this simulator to:
- Explore how **sequence composition**, **ionic strength**, and **strand concentration** affect melting behavior.  
- See how melting curves form from realistic thermodynamic data.  
- Inspect each base’s stability using an interactive color map.  
- Learn how temperature translates into molecular denaturation.

---

## 👥 Who It’s For  

| Audience | What They Can Do |
|-----------|------------------|
| **Students & Educators** | Visualize how GC content and salt concentration influence Tm. |
| **Researchers & Biologists** | Generate predicted melting profiles for custom sequences. |
| **Developers & Modelers** | Study a practical browser implementation of physical chemistry algorithms. |

---

## 🚀 Getting Started  

### ✅ Requirements  
- Modern web browser (Chrome, Edge, or Firefox recommended).  
- No installation or server – runs entirely offline.  

### 💡 Launch Steps  
1. Download or clone the repository.  
2. Open **`App1.html`** in your browser.  
3. The simulator loads instantly with default settings.  
4. Begin typing or pasting a DNA sequence and adjusting parameters.  
5. The visualization updates automatically – no Run button needed.

---

## 🧩 Interface Overview  

The simulator window is split into two main areas:

| Panel | Description |
|--------|--------------|
| **Inputs (left)** | Enter sequences and change physical/experimental parameters. |
| **Visualization (right)** | See the computed melting curve and base-pair map update in real time. |

---

## 🧮 Input Panel – How to Use Every Control  

| Control | What It Does | How to Use It | Default |
|----------|--------------|---------------|----------|
| **DNA Sequence (A/T/G/C)** | Defines the double-stranded region being simulated. | Click inside the text box and type or paste a sequence containing only A, T, G, C (uppercase or lowercase). Invalid characters are ignored automatically. Short sequences (< 10 bp) yield sharp transitions; longer ones (> 100 bp) produce smoother curves. | `ATGCGCATTAATCGGATGCC` |
| **[Na⁺] (M)** | Sodium-ion concentration that stabilizes the duplex. | Enter a value between 0.001 and 1.0 M. Increasing Na⁺ raises Tm (by ~16.6 × log₁₀[Na⁺]). Typical physiological value ≈ 0.05 M. | 0.050 M |
| **Strand Concentration (M)** | Total single-strand molar concentration used in thermodynamic calculations. | Lower concentrations simulate more dilute reactions and slightly lower Tm. Typical PCR concentration ≈ 5 × 10⁻⁷ M. | 0.0000005 M |
| **Window Size (bp)** | Number of bases used to compute each local Tm via the sliding-window method. | Must be an **odd** integer between 5 and 51. Smaller window = more local fluctuation; larger window = smoother curve. Try 15 bp for general use. | 15 bp |
| **Inference Mode** | Determines how per-base melt probabilities are smoothed. | Select from the dropdown:  <br> • **Independent:** No smoothing – each base calculated separately.  <br> • **HMM Posterior:** Probabilities smoothed by forward/backward averaging.  <br> • **HMM Viterbi:** Shows most likely state path (0 = bound, 1 = melted). | Independent |

### 🔹 Parameter Usage Tips
- Change one parameter at a time to see its individual effect.  
- Hit **Enter** after typing numeric values to apply them.  
- Invalid or empty inputs automatically revert to the previous valid value.  
- You can experiment live – the graph updates instantly.

---

## 📊 Visualization Panel – How to Read and Use It  

| Feature | What It Shows | How to Use It |
|----------|---------------|---------------|
| **Melting Curve (blue line)** | Fraction of bases melted (0 → 1) vs temperature. The S-shape indicates the transition region. | Watch how the curve shifts upward as Tm increases with GC content or salt. |
| **Y-axis (left)** | Fraction melted scale from 0 to 1. | 0 = fully double-stranded DNA  ·  1 = fully melted. |
| **X-axis (bottom)** | Temperature in °C (20 – 100 °C). | Hover to read approximate fraction values. |
| **Vertical Dashed Line** | Current temperature selected by the slider. | Move the slider to sweep across the curve and see real-time melting. |
| **Temperature Slider** | Controls the temperature for the visualization. | Drag the handle left/right to change T. Displays exact temperature and percent melted below. |
| **Base-Pair Color Strip** | Visual map of the sequence. Each square represents one nucleotide. Colors fade from blue (dsDNA) to red (ssDNA). | As you increase temperature, observe which regions melt first (A/T-rich) and which stay stable (G/C-rich). |
| **Percent Melted Label** | Displays overall fraction of bases currently melted. | Updates continuously as you move the slider. 100 % = fully denatured. |

---

## 🧠 Step-by-Step Walkthrough  

1. **Start the App**  
   Open `App1.html`. Default sequence loads with initial curve.  

2. **Enter Your Sequence**  
   Paste any DNA string (e.g., `GCGTTAGCGCATATCGCGGTT`).  
   The graph recomputes automatically.  

3. **Tune Parameters**  
   - Increase **Na⁺** → curve shifts right (higher Tm).  
   - Lower **Strand conc** → slightly lower Tm.  
   - Change **Window size** → see curve smoothness change.  
   - Try different **Inference modes** → observe curve smoothing.  

4. **Move Temperature Slider**  
   Slowly drag from 20 °C to 100 °C.  
   Watch the curve and color strip respond in real time.  

5. **Interpret Results**  
   - At low T, fraction ≈ 0 → DNA fully bound.  
   - Near transition, fraction ≈ 0.5 → half of the duplex melted → **Tm**.  
   - At high T, fraction ≈ 1 → completely denatured.  

---

## 🧩 Interpreting Changes in Parameters  

| Parameter Changed | What You’ll See | Why It Happens |
|--------------------|-----------------|----------------|
| **Increase GC content** | Curve moves right → higher Tm | GC pairs have 3 H-bonds vs 2 in AT. |
| **Increase sequence length** | Curve broadens and rises | More base interactions increase stability. |
| **Increase [Na⁺]** | Right shift of curve (higher Tm) | Cations shield negative phosphates. |
| **Decrease [Na⁺]** | Left shift (lower Tm) | Reduced ionic stabilization. |
| **Smaller window size** | More wiggly curve | Higher resolution of local Tm variations. |
| **Switch to HMM Posterior** | Curve and strip smooth out | Hidden Markov averaging removes noise. |

---

## 🧮 Thermodynamic Model  

The simulator uses nearest-neighbor enthalpy (ΔH) and entropy (ΔS) values from SantaLucia (1998).  
Each dinucleotide step adds to the total ΔH and ΔS.  
The melting temperature for each segment is calculated as:

\`\`\`text
Tm (°C) = (ΔH × 1000) / (ΔS + R ln(Ct / 4)) – 273.15 + 16.6 log₁₀[Na⁺]
\`\`\`

where *R* is the gas constant and *Ct* is strand concentration.  
HMM inference is applied after these calculations to produce continuous melting regions for visualization.

---

## 💡 Tips for Effective Use  

- Keep sequence length 20–200 bp for clear curves.  
- Avoid unrealistic ion levels (< 0.001 M or > 1 M).  
- Use stepwise changes to see how each variable influences Tm.  
- Observe melting order on the color strip to identify A/T-rich weak spots.  
- Resize the window freely – the plot and strip adjust automatically.  

---

## 🧱 Planned Improvements  

| Feature | Description |
|----------|-------------|
| 🧮 Multi-sequence comparison | Overlay curves for two DNA samples. |
| 🧫 Salt effect demo | Toggle between Na⁺ and Mg²⁺ models. |
| 💾 Export options | Save curves as CSV or PNG images. |
| 🎓 Teaching modes | Pre-configured lesson scenarios. |

---

## 🧩 Summary  

The **DNA Melting Curve Simulator** transforms the physics of DNA denaturation into an interactive learning experience.  
By modifying simple inputs like sequence and salt concentration, users see in real time how stability changes and where melting occurs.  

Perfect for use in **molecular biology**, **bioinformatics**, and **biotechnology** education or research.

---





