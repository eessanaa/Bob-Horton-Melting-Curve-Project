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
- “You increase Na⁺ from 0.05 M to 0.15 M in the app. Predict and confirm the difference in the plot; justify using thermodynamic reasoning.”
- “Two sequences have identical GC% but different base order. Use the app to show how it alters the curve.”
- “Your app shows two derivative peaks for a sequence. What experimental scenarios could cause this, and how would you troubleshoot in qPCR?”


----------------------------------------------------------------------------------------------------------------------------------------------------------

# Exercise: Identify Sequences from Melting Curves
Use the **DNA Melting Curve Simulator (App2)** as the primary tool and **uMelt** as a reference. You will run two mini-investigations:

- **Part A — Mutated vs Wild-Type (single-base change)**
- **Part B — Different Strains of the Same Organism (sequence variants)**

Keep ionic conditions **constant within each comparison** so differences come from sequence, not parameter changes.

---

## Part A — Mutated vs Wild-Type 

### Given sequences (simple example)
- **Wild-type (WT):** `ATGCGTACCGTAACTGGA`  
- **Mutant (SNP):**  `ATGCGTACCATAACTGGA`  *(G→A at position 10)*

### What to do
1) Open the app  
   - Set **Na⁺ = 0.05 M**, **Mg²⁺ = 0.005 M**, **Start = 40 °C**, **End = 95 °C**, **Step = 1 °C**.  
2) Paste **WT**, observe both curves; then paste **Mutant** under the same conditions.  
3) For each sequence, note:
   - **Tm_app** = temperature at the **peak of the blue derivative** curve.  
   - Curve **shape** (sharp vs broad, single vs double transition).  
4) (Optional) Open **uMelt** with Na⁺ = 50 mM, Mg²⁺ = 0 mM, DMSO = 0%. Record **Tm_uMelt** for both --> To double check the results.

### What to answer
- Which sequence shows the **higher Tm**? Which has the **sharper peak**?  
- Based on Tm and peak shape, **which one is wild-type and which is mutant**? Why?  
- If you increase Na⁺ to **0.15 M** in the app for the *same* sequence, how does Tm shift, and why?

**Expected pattern:** the mutant (with a destabilizing base change) tends to be weaker so it has **lower Tm** (Less heat needed to seperate the strands).

---

## Part B — Different Strains (variant identification) --> Just how COVID has different variants.

### Given variant-like sequences (synthetic, equal length)
- **Strain A:** `GCTTAGGACCTGATCGTA`  
- **Strain B:** `GCTCAGGACCTGATGGTA`  *(two substitutions)*  
- **Strain C:** `GCTTAGGACATGATCGTA`  *(one substitution reducing GC)* --> How long should they be?

### What to do
1) In the app, use **the same ionic settings** for all three strains (e.g., Na⁺ = 0.05 M, Mg²⁺ = 0.005 M).  
2) For each strain, record:
   - **Tm_app** (derivative peak temperature).  
   - Any notes on **peak count/width** and **fraction-melted S-curve**.  
3) (Optional) Check each sequence in **uMelt** (Na⁺ = 50 mM; Mg²⁺ = 0 mM) and note **Tm_uMelt**.

### What to answer
- Order the strains by **increasing Tm** and explain how **GC content / nearest-neighbor context** could cause the ranking.  
- If two strains have the **same GC%** but different **peak shapes** or **slightly different Tm**, what model feature explains that?  
- Propose a simple **decision rule** (e.g., “if Tm ≥ X °C under these conditions, call it Strain B”) and justify it.

---

## Reporting (what to submit)
- **Table** of Tm_app values for each sequence (and Tm_uMelt if you used it).  
- 1–2 **screenshots** from the app showing representative curves.  
- A **summary** (6–10 sentences) explaining which sequence is WT vs Mutant (Part A) and how you distinguished strains (Part B).  
- (Optional) A brief note on how changing **Na⁺/Mg²⁺** would modify your decision thresholds.

---

*Currently thinking of word problems we can add here, e.g.:*
- “You observe **two derivative peaks** for a variant — list two experimental causes and how you’d troubleshoot in qPCR.”  
- “Design a threshold: if **Na⁺ triples**, how should your **Tm cutoff** and why?”





