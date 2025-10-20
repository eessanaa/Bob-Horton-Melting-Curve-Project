#  Graduate Exercise — DNA Melting Temperature (Wallace vs App vs uMelt)

## Objective
Use the **DNA Melting Curve Simulator** (Week_4_App2_DNA_Melting_Curve.html), the **Wallace equation**, and **uMelt** to:
1) Estimate melting temperatures (Tm) for several sequences
2) Compare model outputs
3) Explain how sequence composition and salt affect melting behavior

---

## Background (brief)
- **Wallace rule (quick estimate for short oligos):**  
  Tm (°C) = 2 × (A + T) + 4 × (G + C)
- Works only for certain lengths of sequences (about 14–20 base pairs)
- The **App** uses nearest-neighbor thermodynamics + HMM smoothing to produce fraction-melted and derivative curves.
- **uMelt** generates reference melting curves with ionic parameters (Na⁺, Mg²⁺, DMSO).

---

## Sequences
Use four distinct sequences covering low, medium, and high GC, plus one mixed sequence.

- Seq 1 (AT-rich): `ATATATATATATATAT`
- Seq 2 (GC-rich): `GCGCGCGCGCGCGCGC`
- Seq 3 (Balanced): `AATTGGCCAATTGGCC`
- Seq 4 (Mixed): `AGCTTGACCGTAAGCTTGC`

*(You may substitute your own, but keep lengths ~14–20 bp for Wallace.)*

---

## Part 1 — Wallace Equation (manual)
For each sequence:
1. Count A, T, G, C.
2. Compute **Tm_wallace = 2*(A+T) + 4*(G+C)**.
3. Record the result.

Keep a simple note for each (e.g., “Seq 2 has higher GC → higher Tm expected”).

---

## Part 2 — Simulator App (primary)
1. Open **the app** in your browser.
2. Parameters (unless exploring):  
   - Na⁺ = **0.05 M**  
   - Mg²⁺ = **0.005 M**  
   - Start = **40 °C**, End = **95 °C**, Step = **1 °C**
3. For each sequence:
   - Paste the sequence in the input.
   - Observe **Fraction Melted** (red) and **d(Fraction)/dT** (blue).
   - **App Tm** = temperature at the **peak of the blue derivative** curve.
   - Jot 1–2 notes about curve shape (e.g., sharp vs broad, multiple transitions).
4. (Optional) Change Na⁺ or Mg²⁺ to see how Tm shifts; note the direction of change.

---

## Part 3 — uMelt (reference)
1. Open uMelt: https://www.dna-utah.org/umelt/quartz/um.php
2. For each sequence, set: **Na⁺ = 50 mM**, **Mg²⁺ = 0 mM**, **DMSO = 0%**.
3. Generate the melting curve and record **Tm_uMelt** (peak temperature).

---

## Part 4 — Compare & Explain
For each sequence, you should now have:
- **Tm_wallace** (Part 1)
- **Tm_app (derivative peak)** (Part 2)
- **Tm_uMelt** (Part 3)

Write a short comparison (5–8 sentences total):
- Rank the three Tm values from lowest → highest; comment on consistency.
- Relate differences to **GC%**, **nearest-neighbor stacking**, and **ionic conditions**.
- If you varied Na⁺ or Mg²⁺ in the app, state how Tm moved and why.

---

## What to Submit
- A brief summary listing Tm_wallace, Tm_app, and Tm_uMelt for each sequence.
- 1 paragraph (5–8 sentences) comparing methods and explaining differences.
- (Optional) 1 screenshot of the app curves for any one sequence.

---

## Hints
- Wallace is a **quick** estimate; expect divergence for longer GC-rich sequences or when ionic effects matter.
- The **derivative peak** in the app is your best experimental analog to Tm.
- Increasing **salt** generally **raises** Tm (stabilizes duplex).

---

## Currently thinking of word problems (examples)
- “Given two primers of equal length (Primer A: 30% GC, Primer B: 60% GC), predict which has higher Tm by Wallace, then validate with the app and explain any discrepancy.”
- “You increase Na⁺ from 0.05 M to 0.15 M in the app. Predict and confirm the direction/magnitude of Tm shift; justify using thermodynamic reasoning.”
- “Two sequences have identical GC% but different base order. Use the app to show how nearest-neighbor context alters Tm compared to Wallace.”
- “Your app shows two derivative peaks for a sequence. What experimental scenarios could cause this, and how would you troubleshoot in qPCR?”


