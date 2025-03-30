# CFD Case Setup – Spray Combustion in Pintle Injector

This folder documents the setup parameters, solver configurations, and mesh details used in ANSYS Fluent to simulate spray combustion in a coaxial pintle injector, as part of my undergraduate thesis and ILASS-America 2021 presentation.

---

## 🔧 Geometry and Mesh

- Software: ANSYS DesignModeler + Meshing
- Domain: 2D axisymmetric combustion chamber with pintle injector head
- Features: Inner fuel jet, annular oxidizer, recirculation zone
- Mesh Type: Mapped face mesh with boundary inflation
- Mesh Count: ~75,000 cells
- Mesh Quality: Skewness < 0.85, Aspect Ratio < 3

---

## ⚙️ Solver Setup

- Solver Type: Pressure-based, steady-state
- Gravity: Enabled (–9.81 m/s² along axis)
- Energy Equation: Enabled
- Turbulence: Realizable k-ε model with enhanced wall treatment
- Discrete Phase: DPM with WAVE and TAB breakup models
- Radiation: P1 model (optional for heat loss modeling)

---

## 🔥 Combustion Model

- Model: Species Transport with Eddy Dissipation + Finite Rate
- Reactions: Global 1-step reaction mechanism using H2/O2 or CH4/O2 (depending on run)
- Properties: Thermochemical properties taken from NASA CEA outputs
- Injection: Droplets injected from fuel inlet (30–50 μm SMD)

---

## 🧪 Boundary Conditions

| Boundary       | Type               | Values                                 |
|----------------|--------------------|----------------------------------------|
| Inlet (Fuel)   | Mass Flow Inlet    | 0.012 kg/s, 300 K                      |
| Inlet (Oxid.)  | Velocity Inlet     | 25 m/s, 300 K                          |
| Walls          | No-slip            | Adiabatic                              |
| Outlet         | Pressure Outlet    | 1 atm (0 gauge)                        |

---

## 📊 Convergence Criteria

- Energy residual: 1e-6  
- Momentum, Turbulence: 1e-5  
- Species: 1e-5  
- Converged typically in 800–1200 iterations  
- Monitored flame stabilization and thermal plume shape
