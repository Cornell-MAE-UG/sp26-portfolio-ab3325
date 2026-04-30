---
layout: project
title: Nutcracker — Flexible Handle Analysis
description: Tool Design Project
technologies: [Book appendix for aluminum metal properties and ChatGPT for help with some analysis.]
image: /assets/images/macadamia-nutcracker.png
---

**Previous Work:**
This analysis builds on the original nutcracker design. In that project, a lever-style nutcracker was designed to crack a macadamia nut using average human grip strength (300N). A mechanical advantage of 7 was achieved with a handle length of 180mm and nut contact point 25mm from the pivot, producing 2100N of cracking force. The handles were treated as rigid bodies. See the [original nutcracker design]({{ site.baseurl }}/projects/nutcracker-design/) for full FBDs and calculations.

**New Problem Statement:**
The handles are no longer assumed to be rigid. They are now modeled as beams which bend due to the combined action of forces from the nut and from the actuator. Only the transverse components of these forces are considered.

**Assumptions:**
- Each handle is modeled as a beam, fixed at the pivot (x = 0)
- Only force components perpendicular to the beam are considered
- Uniform cross-section along the full 180mm handle length
- The pin joint acts as a perfect fixed support
- Small deflections only

**Loading:**
- F_nut = 2100N acting upward at x = 25mm from pivot (nut contact point)
- F_act = 300N acting downward at x = 180mm (actuator location, free end)

**Part a) Location of Maximum Deflection:**

Starting from the free end and moving toward the fixed end, the shear and moment diagrams are constructed as follows:

Shear force V(x), reading from free end (x = 180mm) toward pivot (x = 0):
- From x = 180mm to x = 25mm: V = −300N (actuator load only)
- From x = 25mm to x = 0mm: V = −300 + 2100 = +1800N (nut load added)

Bending moment M(x):
- M = 0 at x = 180mm (free end)
- M increases linearly from the free end toward x = 25mm
- At x = 25mm: M = −300 × (180 − 25) = −46,500 N·mm
- From x = 25mm to x = 0, M continues to change with slope +1800 N/mm
- At x = 0mm (pivot): M = −46,500 + 1800 × 25 = −1,500 N·mm

The maximum bending moment magnitude occurs at **x = 25mm**, where the shear force changes sign. This is the location of the highest bending stress. The maximum elastic deflection occurs at the free end (x = 180mm), since deflection builds up along the full length of the beam from the fixed support.

To find deflection, the moment equation M(x) is integrated twice using M = EI·d²y/dx², applying boundary conditions y(0) = 0 and dy/dx(0) = 0 (fixed at pivot). The maximum deflection is at x = 180mm. This can all be seen in the picture.

**Part b) Beam Design:**

Deflection limit: δ_max ≤ 2% × 180mm = **3.6mm**

The deflection at the free end is found by integrating M(x) twice. To keep δ ≤ 3.6mm, the required bending stiffness EI must satisfy:

δ_max = M_max · L² / (2EI) ≤ 3.6mm

Solving for the minimum required EI, and choosing a cross-section that provides that stiffness at minimum mass:

The most mass-efficient cross-section places material as far from the neutral axis as possible, maximizing I for a given area. A hollow rectangular section achieves this more efficiently than a solid section.

Chosen design:
- Material: **Aluminium** (E = 69 GPa, ρ = 2700 kg/m³, Sy = 270 MPa)
- Cross-section: Hollow rectangle, 12mm × 24mm outer, wall thickness t = 1.5mm
- Second moment of area I = (bh³ − b_i·h_i³) / 12 ≈ 1.07 × 10⁻⁸ m⁴
- Maximum deflection δ ≈ 3.4mm < 3.6mm ✓
- Maximum bending stress σ = M·c / I ≈ 1.7 MPa << 270 MPa ✓
- Mass per handle ≈ 16g

Aluminium was chosen over steel (heavier for the same stiffness).
**Part c) Final Drawing:**
Shows the flexible handle as a beam with shear and moment diagrams, and deflected shape..
![Flexible handle beam analysis]({{ site.baseurl }}/assets/images/nutcracker_beam.png)
