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

**Created for educational and research purposes — bridging DNA thermodynamics and interactive visual learning.**
