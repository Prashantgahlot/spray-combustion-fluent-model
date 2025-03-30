# Spray Combustion Simulation – Pintle Injector Model

This repository contains the numerical setup, simulation notes, and post-processing results for a pintle injector-based combustion system, originally developed as part of my Bachelor’s thesis and later presented at ILASS-America 2021.

---

## 🧪 Project Overview

The goal of this project is to simulate spray atomization, droplet breakup, and combustion in a coaxial pintle injector configuration using ANSYS Fluent and thermochemical data from NASA CEA. The work models primary breakup physics and flame stabilization characteristics under green propellant conditions.

---

## 🔧 Methodology

- **Preprocessing:**
  - Thermochemical properties calculated using NASA CEA
  - Geometry and mesh setup in ANSYS Meshing

- **Solver Setup:**
  - Turbulence: Realizable k-ε
  - Combustion: Species Transport + Finite Rate/Eddy Dissipation
  - Spray breakup: DPM with Wave and Taylor Analogy Breakup models
  - Radiation model: P1 (optional)
  
- **Boundary Conditions:**
  - Inlet: Fuel/Oxidizer spray input with defined droplet distributions
  - Outlet: Pressure-outlet boundary

---

## 📊 Results (Planned Uploads)

- Velocity vector fields  
- Temperature contour plots  
- Sauter Mean Diameter (SMD) analysis  
- Pressure and flame front distribution

📌 *Visuals and result images will be uploaded to `/results` folder soon.*

---

## 🧠 Future Directions

- Coupling with OpenFOAM-based models for transient multiphase simulations  
- Development of surrogate models using regression & ML tools (TensorFlow)  
- Parameter sweep and optimization studies for injector design

---

## 📄 File Structure

```bash
├── case-files/               # Fluent case and data files (to be uploaded)
├── results/                  # Images and post-processing outputs
├── ILASS2021_Abstract.pdf    # Conference abstract (already presented)
├── nasa-cea-input.txt        # Example propellant input file
└── README.md                 # This file
