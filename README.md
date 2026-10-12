# Static Structural Analysis of an Axle Gearbox Housing ⚙️

![ANSYS](https://img.shields.io/badge/Simulation-ANSYS_Workbench-blue)
![FEA](https://img.shields.io/badge/Analysis-Static_Structural-orange)

## 📌 Project Overview
This repository contains a comprehensive finite element analysis (FEA) of an axle gearbox housing subjected to an operational bearing load of **50 kN**. To optimize computational resources while maintaining high fidelity, a half-symmetry model was utilized. 

The primary goal of this project was to validate the structural integrity of the housing, distinguish true stress concentrations from artificial mesh singularities, and extract critical reaction forces to recommend design improvements.

## 🎯 Objectives
* **Load Path Validation:** Apply a 50 kN asymmetric load and evaluate internal cutting moments.
* **Singularity Evaluation:** Utilize localized mesh refinement (Sphere of Influence) and path evaluations to verify stress hotspots.
* **Force Extraction:** Map nodal reaction forces at individual mounting holes to validate the structural load path.

## 🛠️ Methodology & Setup
* **Material:** Structural Steel (Yield Strength: 260 MPa).
* **Contacts:** Bonded contacts representing the physical stiffness of the assembled drivetrain components.
* **Boundary Conditions:** 
  * Frictionless support applied to the half-symmetry cut plane.
  * Fixed supports applied to 3.5 rear mounting bolt locations (representing 7 physical bolts).
* **Meshing:** Global mesh of 10mm, with targeted localized face sizing (1mm) and Sphere of Influence refinement (2mm) at critical stress regions.

## 📊 Key Findings

1. **Maximum Stress & Safety Factor:** The maximum equivalent (von-Mises) stress stabilized at **135 MPa** after mesh refinement. This results in a minimum **Factor of Safety of 1.93** against yield, indicating the structure is robust.
2. **Singularity Ruled Out:** Edge path stress evaluation demonstrated a uniform, smooth stress gradient peaking at 110 MPa, confirming the hotspot is a legitimate physical stress concentration, not a numerical singularity.
3. **Internal Bending Moment:** The 50 kN offset shear load induces a massive **6000 Nm bending moment** across the structural cut plane.
4. **Bolt Load Distribution:** Because of the induced moment, the upper-most mounting hole absorbs the vast majority of the reaction load (**40.9 kN in tension**). This perfectly correlates with the 135 MPa stress hotspot located directly adjacent to this bolt.

## 💡 Recommendations for Design Improvement
Based on the simulation data, the following design optimizations are proposed:
1. **Relocate Upper Mounting Hole:** If the assembly envelope permits, relocating the upper bolt slightly outward would distribute the 40.9 kN reaction force more evenly and significantly reduce the primary stress hotspot.
2. **Edge Filleting:** Adding a small radius to the sharp edges at the rear housing will alleviate localized stress risers and improve fatigue life.

## 📁 Repository Structure
* `/CAD_Model` - Contains the neutral 3D geometry (STEP format).
* `/ANSYS_Archive` - Contains the compressed `.wbpz` Ansys Workbench archive.
* `/Documentation` - Contains the full, detailed PDF Engineering Report.
* `/Images` - Simulation contour plots and graphs.

---
*Project completed by sachin salaskar* | *https://www.linkedin.com/in/sachinsalaskar10/*# Gearbox-FEA-Analysis
