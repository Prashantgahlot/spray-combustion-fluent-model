# ANSYS Fluent Setup Notes – Pintle Injector Simulation

This file outlines the detailed Fluent configuration used for simulating spray combustion inside a coaxial pintle injector. The goal was to capture droplet breakup, combustion stability, and flame characteristics using a species-based combustion model with discrete phase injection.

---

## 🧰 Solver Settings

- **Solver Type**: Pressure-Based  
- **Time**: Steady  
- **Gravity**: Enabled (–9.81 m/s², Y-axis for 2D axisymmetric)  
- **2D Axisymmetric**: Yes  

---

## 🌡️ Models Enabled

| Category        | Model                             | Notes                          |
|----------------|------------------------------------|--------------------------------|
| Energy          | Enabled                            | Required for combustion        |
| Viscous         | Realizable k-ε + Enhanced wall     | Good balance for recirculation zones |
| Combustion      | Species Transport + Finite Rate / Eddy Dissipation | Captures reaction + mixing limited flame behavior |
| DPM             | On (spray breakup)                 | WAVE + TAB breakup models used |
| Radiation       | P1 (optional runs)                 | For estimating radiative heat losses |

---

## 🔬 Materials and Reactions

- **Fuel**: H2, CH4, or custom hydrocarbon from NASA CEA  
- **Oxidizer**: O2  
- **Reactions**: One-step global (e.g., CH4 + 2O2 → CO2 + 2H2O)  
- **Thermo Data**: Thermodynamic properties imported from NASA CEA output

---

## 🚀 Discrete Phase (DPM) Settings

- **Injection Type**: Surface  
- **Spray Source**: Fuel inlet  
- **Droplet Size**: SMD ~30–50 μm  
- **Breakup Models**: WAVE + TAB (default tuning)  
- **Interaction with Continuous Phase**: Enabled  
- **Coupled Flow**: Two-way

---

## 🔃 Boundary Conditions Summary

| Name         | Type            | Values                            |
|--------------|------------------|-----------------------------------|
| Inlet – Oxidizer | Velocity Inlet | 25 m/s, 300 K, O2                 |
| Inlet – Fuel     | Mass Flow Inlet (DPM) | 0.012 kg/s, spray injection |
| Wall          | No-slip, adiabatic  | Enhanced wall treatment         |
| Outlet        | Pressure Outlet     | 1 atm, backflow temp 300 K       |

---

## 📊 Monitors and Convergence

- Residuals:
  - Energy: 1e-6  
  - Continuity, Momentum, Turbulence, Species: 1e-5  
- Monitors:
  - Flame temperature profile  
  - CH4/H2O mass fraction along centerline  
  - DPM injection behavior

---

## 📝 Notes

- Inlet conditions varied for each propellant setup (see `/cea-outputs/`)  
- Mesh refinement tested at injector interface and flame stabilization zone  
- Future runs will include transient behavior and OpenFOAM comparison

---

## 📬 Contact

For questions or simulation reproduction:  
📧 [prashant.gahlot@studio.unibo.it](mailto:prashant.gahlot@studio.unibo.it)
