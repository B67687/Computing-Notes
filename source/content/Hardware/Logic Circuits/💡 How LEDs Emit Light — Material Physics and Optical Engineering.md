## 🧠 Motivation

> [!Why we care]
> LEDs are PN junction diodes that emit light through electroluminescence. But unlike regular diodes, they’re engineered to convert electrical energy into visible photons efficiently.
>
> This note scaffolds the physics, material choices, and design optimizations that make LEDs possible—and powerful.

---

## 🔬 Core Principle: Electroluminescence

- In forward bias, electrons from the **N-type** region recombine with holes in the **P-type** region.
- In **direct band gap materials**, this recombination releases energy as **photons** (light).
- In **indirect band gap materials** (like silicon), energy is lost as **heat** instead.

> 🧠 LEDs use **direct band gap semiconductors** to favor radiative recombination.

---

## 🧪 Material Engineering

| Material         | Band Gap (eV) | Color Emitted | Notes                          |
|------------------|---------------|----------------|--------------------------------|
| GaAs             | ~1.4          | Infrared       | Early LEDs, low visibility     |
| AlGaAs           | ~1.9          | Red            | Common in indicator LEDs       |
| InGaN            | ~2.3–2.7      | Green–Blue     | Used in modern high-brightness LEDs |
| GaN              | ~3.4          | Blue–UV        | Basis for white LEDs via phosphor |

> Direct band gap materials allow photon emission without phonon assistance.

---

## 🧱 Fabrication Techniques

### 🔹 Epitaxial Growth

- Thin layers of semiconductor are grown on substrates like **sapphire** or **SiC**.
- Ensures crystal alignment and minimal defects.

### 🔹 Doping and Junction Formation

- Controlled doping creates the **P-type and N-type** regions.
- Junction is tuned to maximize recombination in the **active layer**.

---

## 🔍 Optical Optimization

| Technique              | Purpose                         |
|------------------------|----------------------------------|
| Dome-shaped lenses     | Extract trapped photons          |
| Reflective layers      | Bounce light outward             |
| Surface texturing      | Reduce internal reflection       |
| Phosphor coating       | Convert blue/UV to white light   |

> These physical alterations amplify visible light and minimize loss.

---

## 🎨 Color Tuning and Perception

- **Band gap energy** determines photon wavelength (color).
- **Phosphor coatings** re-emit absorbed photons at broader wavelengths → perceived as white.
- **RGB mixing** also used in display tech for full-spectrum control.
