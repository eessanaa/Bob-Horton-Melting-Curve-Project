# Science Behind DNA Melting Curves

## Technical Background — DNA Thermodynamics

DNA molecules consist of two complementary strands held together by **hydrogen bonds** and **base stacking interactions**.

- **Hydrogen bonds** connect complementary bases (A–T pairs form two bonds, G–C pairs form three).
  - More bonds = stronger pairing, so GC-rich DNA requires higher temperature to separate.
- **Base stacking** adds extra stability between layers of paired bases.
  - Imagine a stack of cards—each base pair presses against the next, creating additional stability in the double helix.

### Enthalpy (ΔH)

- Represents the **heat energy** required to break hydrogen bonds and stacking interactions.
- GC-rich sequences have higher ΔH, meaning they require more energy to melt.
- This explains why scientists describe GC-rich DNA as “more stable.”

### Entropy (ΔS)

- Measures the **disorder** in a system.
- When DNA melts, the ordered double helix becomes two free single strands, increasing entropy.
- At higher temperatures, the gain in entropy drives melting to occur more readily.

### Free Energy (ΔG = ΔH – TΔS)

- Determines whether melting is thermodynamically favorable.
- When ΔG becomes **negative**, melting occurs spontaneously.
- The balance between bond strength (ΔH) and disorder (ΔS) controls overall stability.

### Melting Temperature (Tm)

- Defined as the temperature at which **half of the DNA molecules are melted**.
- Factors that affect Tm:
  - **GC content:** higher GC = higher Tm.
  - **Salt concentration:** salts stabilize the negatively charged backbone; low salt makes melting easier.
  - **DNA length:** longer sequences melt at higher Tm because more bonds must be broken.
- In **PCR**, knowing Tm ensures primers bind at the right temperature for efficient amplification.

### Nearest-Neighbor Model

- DNA melting depends not just on GC vs AT ratio, but also on **neighboring base interactions**.
- Example: a GC base next to another GC is more stable than GC next to AT.
- The **nearest-neighbor model** calculates stability more accurately by including these local effects.

---

## Application of Melting Curves in qPCR

### What is a Melting Curve?

- A **melting curve** shows how DNA transitions from double- to single-stranded as temperature increases.
- It typically forms an **S-shaped curve**:
  - Low temperature → fully double-stranded.
  - High temperature → fully single-stranded.
  - Mid-range → partial melting.

### First Derivative Curve (dF/dT)

- Plots the **rate of fluorescence change** with temperature.
- Produces sharp **peaks** showing where DNA melts fastest.
  - Each peak corresponds to a unique DNA fragment with a specific Tm.

### Why It Matters in qPCR

- In **quantitative PCR**, melting curves are used to verify product specificity after amplification.
  - **Single peak:** one clean, correct product.
  - **Multiple peaks:** unwanted byproducts or primer-dimers.
- This makes melting curve analysis an essential **quality control** tool in both research and diagnostics.

### Experimental Workflow

1. After PCR, the sample is gradually heated.  
2. Fluorescent dyes (e.g., SYBR Green) bind to double-stranded DNA.  
3. As the DNA melts, the dye is released and fluorescence decreases.  
4. The recorded fluorescence drop produces a **melting curve**.  
   - Sharp transition = pure product.  
   - Multiple transitions = contamination or secondary structures.

### Role of the Simulator

- The simulator models melting using **nearest-neighbor thermodynamics** to calculate theoretical curves.
- Users can test **what-if** conditions, such as:
  - “What if GC content increases?”
  - “What if salt concentration decreases?”
- These simulations allow visualization of DNA thermodynamics without expensive lab equipment.
- Ideal for **undergraduate, graduate, and teaching labs** to connect theory with practical understanding.