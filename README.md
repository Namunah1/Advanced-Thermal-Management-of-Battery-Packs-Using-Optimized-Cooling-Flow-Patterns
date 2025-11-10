
***

# Advanced Thermal Management of  Battery Pack Using Hybrid Cooling Strategies

## Abstract

This repository presents a comprehensive CFD-based study of battery thermal management. Three cooling strategies—water-based convective, immersed-water hybrid, and active serpentine liquid cooling—are modeled and compared for efficiency, uniformity, and energy consumption. The goal is to guide the design of optimal battery thermal management systems (BTMS) for electric vehicles and energy storage.

## Repository Contents

| File Name                                 | Description                                                   |
|--------------------------------------------|---------------------------------------------------------------|
| Battery Active Serpentine Flow Cooling.wbpj    | CFD project: active liquid serpentine cooling                 |
| Battery Air-Based Convective Cooling.wbpj      | CFD project: forced air cooling                              |
| Immersed Water Cooling for Battery Pack.wbpj     | CFD project: Immersed Cooling                  |
| README.md                                 | Documentation and simulation summary                         |

## Simulation Setup & Boundary Conditions

All simulation models share consistent geometric, physical, and numerical parameters to enable direct performance comparison.

**Geometry and Mesh**
- Prismatic battery cells arranged in a rectangular module
- Structured hexahedral mesh refined at solid–fluid boundaries
- Grid independence ensured (<1% max cell temperature change)

**Boundary and Initial Conditions**

| Parameter                  | Value / Description                               |
|----------------------------|--------------------------------------------------|
| Inlet velocity (liquid)    | 0.5–1 m/s                                        |
| Inlet temperature          | 290 K (25 °C)                                    |
| Outlet                     | Pressure outlet (0 Pa gauge)                     |
| Wall                       | No-slip, adiabatic                               |
| Cell exterior              | Coupled wall (conjugate heat transfer enabled)   |
| Coolant (water)        | Standard properties at 25 °C                     |

**Numerical Methods**
- Solver: Steady-state, pressure-based
- Energy equation: Enabled
- Turbulence: Realizable k–ε model (enhanced wall treatment)
- Discretization: Second-order upwind
- Convergence: $$10^{-6}$$ (energy), $$10^{-4}$$ (continuity/momentum)

## Cooling Strategies Modeled

- **Air-Based Cooling**: Forced convection through channel, best for simplicity.
- **PCM–Air Hybrid Cooling**: Incorporates phase change material to buffer thermal spikes, improves peak temperature regulation.
- **Serpentine Liquid Cooling**: Maximizes heat transfer and temperature uniformity via a coiled liquid channel; achieves minimal ΔT.

## Tools & Software

- ANSYS Fluent/Workbench (2025 R2) – CFD simulation

## How to Use

1. Open desired `.wbpj` file in ANSYS Workbench.
2. Review/edit setup in Fluent as needed.
3. Run simulation for each cooling method.
4. Compare results following the boundary conditions detailed above.

## References

1. Bandhauer, T. M., Garimella, S., & Fuller, T. F. (2011). “A Critical Review of Thermal Issues in Lithium-Ion Batteries.” *Journal of The Electrochemical Society*, 158(3), R1–R25.
2. Wu, W., et al. (2017). “Review on Thermal Management Methods for Lithium-Ion Battery.” *Applied Thermal Engineering*, 115, 259–282.
3. Mills, A. F. (1999). *Heat Transfer* (2nd ed.). Prentice Hall.
4. Khateeb, S. A., et al. (2004). “Design and Simulation of a Lithium-Ion Battery with a Phase Change Material Thermal Management System.” *Journal of Power Sources*, 128(2), 292–307.
