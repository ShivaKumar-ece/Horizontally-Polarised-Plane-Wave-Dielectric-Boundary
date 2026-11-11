# Horizontally Polarised Plane Wave across a Dielectric–Dielectric Boundary

An interactive, browser-based simulator for the reflection and transmission of a **horizontally (parallel) polarised uniform plane wave** at the planar boundary between two lossless dielectric media.

**Live app:** https://shivakumar-ece.github.io/Horizontally-Polarised-Plane-Wave-Dielectric-Boundary/

**Developers:** Shiva, Mohith, Pravallika. Built for the Electromagnetic Waves & Radiating Systems (EWRS) course at IIT Bhubaneswar.

---

## Geometry and conventions

- The boundary is the plane **z = 0**. Medium 1 (z < 0) is on the left and Medium 2 (z > 0) is on the right.
- **x** points up. **H** lies along **±y** (out of or into the screen), so **E** lies in the plane of incidence (horizontal / parallel polarisation).
- Both media are lossless (σ = 0) and are described by εr and μr.

## What the app can do

### 1. Inputs
- **Medium properties:** set εr₁, μr₁, εr₂ and μr₂ with sliders or by typing values (εr up to 200, μr up to 100).
- **Presets:** Air → Glass, Air → Water, Glass → Air (TIR), Water → Air (TIR), Glass → Water, and an impedance-matched case (Air → εr = μr = 4).
- **⇄ Swap media:** flips Medium 1 and Medium 2 in one click.
- **Angle of incidence θi:** 0° to 89.9°, with quick buttons for **Normal (0°)**, **Brewster angle θB** and **Critical angle θc**. A button is disabled when that angle doesn't exist for the chosen media.
- **Incident field peak:** enter either Ei₀ (V/m) or Hi₀ (A/m). The two stay linked through Hi₀ = Ei₀ / η₁.
- **Frequency (GHz):** sets ω, β, λ and the time scale.

### 2. Animation of incident, reflected and transmitted waves
- A live animation of all three waves showing **E (red)**, **H (blue)** and the **propagation direction k̂ (green)**, with angle markers for θi, θr and θt.
- A background showing the **total Hy field pattern (wavefronts)**, including standing-wave interference in Medium 1 and the evanescent field during TIR.
- H can be drawn as **⊙ / ⊗ symbols** or as **3-D arrows**.
- Each wave (incident, reflected, transmitted) and the background can be turned on or off.
- Playback controls:
  - Play/Pause (also with the **Space** key)
  - Step ±15° in ωt
  - A draggable time slider
  - Speed and zoom controls
- A separate **3-D view of each wave on its own** shows that **E ⊥ H ⊥ k̂**, with all three drawn to the same scale.

### 3. Space and time dependence of the total field
- **Space plot:** Ex, Ez and Hy along the normal (x = 0) at the current instant, with the peak envelope drawn faintly behind.
- **Time plot:** the fields at a movable **probe point z** over two periods.
- Shows the boundary conditions directly: the **tangential components (Ex, Hy) are continuous** across z = 0, while the **normal component Ez jumps** (ε₁Ez₁ = ε₂Ez₂).

### 4. Derived quantities
- Refractive indices n₁ and n₂, intrinsic impedances η₁ and η₂, wavelengths λ₁ and λ₂, phase constants, and the period.
- **Reflection coefficient Γ∥** and **transmission coefficient τ∥**, given as complex magnitude ∠ phase where needed.
- **Power reflectance R** and **transmittance T**, with an energy-conservation check (R + T = 1).
- **Brewster angle θB** (zero reflection for parallel polarisation), with the condition under which it exists.
- **Total internal reflection:** the critical angle θc, the evanescent attenuation constant α and the penetration depth δ = 1/α.
- **Coefficient plots versus angle of incidence** in three tabs: |Γ∥| and |τ∥|, power R and T, and phase. Markers show θB, θc and the current θi, and the TIR region is shaded.
- A short written explanation of what is happening at the current settings.

### 5. Field expressions
- Full time- and space-dependent expressions for the **incident, reflected and transmitted E and H fields**, filled in with the current numerical values.

### 6. Formulas used
- A reference sheet of every relation the app uses:
  - Snell's law
  - η and β for each medium
  - The Fresnel equations for parallel polarisation
  - The Brewster and critical angle formulas
  - The power coefficients
  - The evanescent-wave relations

## Physics cases you can explore
- Rarer → denser incidence (for example, air to glass)
- Denser → rarer incidence, beyond θc, with total internal reflection and an evanescent transmitted wave
- Incidence at the Brewster angle, where reflection becomes zero
- Normal incidence
- Impedance-matched media (η₁ = η₂), where there is no reflection at normal incidence

## How it runs
The app is a single self-contained `index.html` file made of plain HTML, CSS and JavaScript, with no libraries and no external requests. GitHub Pages only serves the file. All computation and drawing happen **in the viewer's own browser**, so nothing is sent to a server.

To run it offline, download `index.html` and open it in any modern browser.
