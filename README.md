# Explicit Dynamics Simulation: Deep Drawing Process

![Project Banner](images/banner_placeholder.jpg)
## 📄 Abstract
**Engineer:** Bishoy Labib | **Type:** Nonlinear Finite Element Analysis (FEA) | **Solver:** Ansys Explicit Dynamics

This project simulates the manufacturing process of deep drawing an aluminum blank into a cylindrical cup. Using Explicit Dynamics, the study analyzes the stress distribution, plastic strain, and deformation behavior of the material. A key focus of this project was the simulation of manufacturing defects—such as tearing, wrinkling, and earing—by manipulating process parameters like punch velocity and friction.

## 🎯 Objective
The primary goal was to create a realistic 3D simulation of the deep drawing process to:
1.  Analyze **Total Deformation** and **Equivalent (Von-Mises) Stress**.
2.  Validate the model using a **Mesh Convergence Study**.
3.  Simulate and identify common manufacturing defects (Tearing, Earing, Wall Wrinkling).

## ⚙️ Simulation Setup

### 1. Geometry & Parts
The assembly consists of four rigid and flexible bodies modeled in 3D:
* **Punch:** Remote displacement (Translation Y only).
* **Die & Blank Holder:** Fixed support (representing clamping force).
* **Blank:** Aluminum sheet (Thickness: 1mm).

### 2. Material Properties
* **Material:** Aluminum (General Non-linear & Explicit).
* **Constitutive Model:** Bilinear Isotropic Hardening.
* **Yield Strength:** 280 MPa.
* **Density:** 2770 kg/m³.

### 3. Boundary Conditions
* **Velocity:** 200 m/s (Applied to Punch).
* **Friction Coefficient:** 0.19 (Static) / 0.1 (Dynamic) between aluminum and steel tools.
* **End Time:** Calculated based on punch travel distance (approx. 0.00019s).

## 🔍 Mesh Convergence Study
To ensure the accuracy of the results independent of the mesh size, a convergence investigation was performed.
* **Strategy:** The blank mesh density was varied while tracking the Maximum Equivalent Stress and Computation Time.
* **Optimization:** A mesh size of **1mm (surface)** and **0.5mm (thickness)** was selected. This ensured the blank was **2 elements thick**, providing accurate deformation results while maintaining acceptable processing time.

![Mesh Convergence Graph](images/mesh_graph_placeholder.jpg)
## 📊 Results

### Equivalent (Von-Mises) Stress
The simulation captured the stress variations throughout the drawing phases.
* **Average Stress:** ~400 MPa.
* **Maximum Stress:** 610.66 MPa (occuring at critical deformation points).

![Stress Results](images/stress_result_placeholder.jpg)
### Plastic Strain
* **Max Plastic Strain:** 0.3986.
* This value remained below the failure strain for the successful drawing iteration, indicating a safe manufacturing process.

## 💥 Defect Simulation
A significant portion of this project involved intentionally inducing failures to study defect modes:

### 1. Tearing (Fracture)
By altering velocity and material limits, the blank locally reached plastic strain failure, resulting in tearing at the cup base.

![Tearing Defect](images/tearing_placeholder.jpg)
### 2. Wrinkling & Earing
* **Wall Wrinkling:** caused by die geometry issues.
* **Earing:** observed at the cup rim, requiring trimming operations in real-world scenarios.

## 🚀 Conclusion
The simulation successfully validated that the deep drawing process for this specific aluminum grade is feasible under controlled friction and velocity parameters. The study highlighted the critical importance of mesh sizing in explicit dynamics, where a balance between element thickness (for bending accuracy) and Courant number (time step size) must be maintained.

---
*Based on the report "Explicit Dynamics Report – Deep Drawing" by Bishoy Labib.*
