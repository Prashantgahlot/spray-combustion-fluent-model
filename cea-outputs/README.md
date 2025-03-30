# NASA CEA Outputs Archive

This directory contains output files generated using NASA's Chemical Equilibrium with Applications (CEA2) software. These outputs were used for parametric studies of propellant combinations and combustion performance in bipropellant and hybrid propulsion systems.

## 🧪 Simulation Parameters

- **Pressure**: 20, 25, 30 bar
- **O/F Ratios**: 2.0, 4.0, 6.0, 8.0, 10.0
- **Oxidizers used**: H₂O (L), CH₃OH (L), NH₃ (L)

## 🔬 Fuel Variants Tested

| Filename                         | Fuel Type             | Notes |
|----------------------------------|------------------------|-------|
| `cea_Sasol0907_OF2-10_P20-30.txt` | Sasol Wax 0907         | C₅₀H₁₀₂, higher paraffin |
| `cea_Sasol6003_OF2-10_P20-30.txt` | Sasol Wax 6003         | C₃₂H₆₆, medium paraffin |
| `cea_Sasol6805_OF2-10_P20-30.txt` | Sasol Wax 6805         | C₄₀H₈₂, mid-high paraffin |
| `cea_Ethanol_OF2-10_P20-30.txt`   | C₂H₅OH (Ethanol)       | Cryogenic/liquid biofuel |
| `cea_Methane_OF2-10_P20-30.txt`   | CH₄ (Methane)          | Common for hybrid modeling |
| `cea_RP1_OF2-10_P20-30.txt`       | RP-1 (Kerosene)        | Benchmark baseline |

## 📌 Usage

These outputs were used to extract:
- Adiabatic flame temperatures  
- Specific impulse (Isp)  
- Characteristic velocity (c*)  
- Product species compositions  
- Reaction trends for hybrid and bipropellant optimization

## 📬 Contact

Prashant Gahlot  
[prashant.gahlot@studio.unibo.it](mailto:prashant.gahlot@studio.unibo.it)  
[ORCID: 0009-0007-2141-181X](https://orcid.org/0009-0007-2141-181X)
