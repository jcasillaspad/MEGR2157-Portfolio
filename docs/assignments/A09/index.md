# A9 – Pulley Drive

> Draft: this page includes the 10 handwritten screenshots currently available (IMG_0359–IMG_0368). Eight of the intended 18 screenshots still need to be added. The missing notes may contain design inputs, selections, or sketches that are not verified here.

## Objective

The objective was to analyze a pulley drive by working through the belt, shaft, journal bearings, and frame. I organized the calculations below with the known values, equations, and results from my handwritten notes.

## Belt

The available power calculation uses a tight-side tension of 6.667 lbf, a slack-side tension of 3.333 lbf, and a belt speed of 1,178.1 ft/min. The difference between the tensions transmits power.

P = (T1 − T2)v / 33,000

P = (6.667 − 3.333)(1,178.1) / 33,000 ≈ 0.119 hp

![Handwritten belt power calculation](IMG_0359.jpeg)

The tension ratio is approximately 2. With an assumed wrap angle of π radians, the friction equation gives:

T1 / T2 ≤ exp(μθ)

μmin = ln(T1 / T2) / θ = ln(2) / π ≈ 0.221

![Handwritten belt friction calculation](IMG_0360.jpeg)

This is the minimum friction coefficient for the stated tension ratio and wrap angle in the simplified friction model. It is not a measured coefficient or a verified belt rating. The missing belt notes are needed to confirm the pulley dimensions, center distance, belt length and cross-section, material selection, and the derivation of the tensions. Belt strength and slip performance have not been verified from the available pages.

## Shaft

**Known Values and Free Body Diagram**

My shaft notes use a torque of 5.00 in-lbf, a speed of 1,500 rpm, a yield strength of 85,000 psi, and a required safety factor of 3. The transverse load used later is 10 lbf. The yield strength is treated as an assumption until the shaft material and condition are confirmed.

The first sketch represents equal and opposite applied torques. The arrows along the shaft are torque labels, not additional axial forces.

![Shaft known values and torque diagram](IMG_0361.jpeg)

**Torsion Calculation**

For a solid circular shaft:

J = πd⁴ / 32

τmax = Tc / J = 16T / (πd³)

Using the von Mises criterion for pure torsion, the allowable shear stress is:

τallow = Sy / (√3 N) = 85,000 / (√3 × 3) ≈ 16,358 psi

Solving for the minimum diameter gives dmin ≈ 0.116 in. I used a shaft diameter of 0.375 in in the following calculations.

![Shaft torsion equations and minimum diameter](IMG_0362.jpeg)

For d = 0.375 in, the shear stress is approximately 483 psi and the torsion-only yield safety factor is 101.6.

![Shaft torsional stress and safety factor](IMG_0363.jpeg)

**Combined Bending and Torsion**

The bearing model below places the 10 lbf load halfway between supports 2.00 in apart. This gives Mmax = Fs / 4 = 5.00 in-lbf.

The bending stress is σb = 32M / (πd³) ≈ 966 psi. Combining bending and torsion gives:

σVM = √(σb² + 3τ²) ≈ 1,278 psi

N = Sy / σVM = 85,000 / 1,278 ≈ 66.5

The combined result is lower than the torsion-only safety factor and is the relevant static yield check for this loading model. It exceeds the required value of 3 under the stated assumptions. These calculations do not check rotating-shaft fatigue, stress concentrations, shaft deflection, or shock loads.

The combined calculation is shown in the screenshot at the end of the journal bearing section, which also contains the PV result.

## Journal Bearing

**Known Values and Free Body Diagram**

I used a 0.375 in shaft diameter, a 2.00 in bearing span, and a bearing length of 0.500 in. The shaft speed is 1,500 rpm. The model assumes two simple supports with the 10 lbf pulley load centered between them.

![Bearing known values and shaft support diagram](IMG_0364.jpeg)

**Bearing Reactions**

From force equilibrium, RA + RB = 10 lbf.

Taking moments about A gives RB(2) − 10(1) = 0. Therefore, RA = RB = 5.00 lbf.

![Handwritten bearing reaction calculation](IMG_0365.jpeg)

**Pressure, Velocity, and PV**

The projected area of each bearing is Ap = dLb = 0.375(0.500) = 0.1875 in².

The pressure on each bearing is p = R / Ap = 5 / 0.1875 ≈ 26.67 psi.

The shaft surface velocity is v = πdn / 12 = π(0.375)(1,500) / 12 ≈ 147.26 ft/min.

![Bearing projected area, pressure, and surface velocity](IMG_0366.jpeg)

PV = pv ≈ 3,927 psi-ft/min.

![Bearing PV and combined shaft bending and torsion calculations](IMG_0367.jpeg)

These values describe the operating demand. A bearing material or part cannot be approved from these numbers alone. Its allowable pressure, speed, and PV must be checked for the intended lubrication and operating conditions. The available screenshots do not identify a verified bearing rating, fit, or clearance.

## Frame

The available frame calculation uses a 2.00 in width, a 0.250 in thickness, and a 5 lbf load. The assumed yield strength is 35,000 psi, with a required safety factor of 3.

A = wt = 2.00(0.250) = 0.500 in²

σ = F / A = 5 / 0.500 = 10.0 psi

σallow = Sy / 3 = 35,000 / 3 ≈ 11,667 psi

The nominal direct-stress safety factor is 35,000 / 10 = 3,500.

![Handwritten frame area and direct stress calculation](IMG_0368.jpeg)

This result only covers direct stress on the assumed area. It does not establish the safety factor of the whole frame. The frame sketch and load path are still needed to check whether the load causes bending, and to assess deflection, connections, and local bearing loads. The frame material also needs to be confirmed.

## Lessons Learned

The calculations show why the belt tension difference and the load on the shaft have different roles. The tension difference transfers power, while the belt forces also load the shaft and its supports.

The shaft results also show why checking torsion alone is not enough. Including bending reduces the calculated yield safety factor from about 101.6 to 66.5.

For the journal bearings, calculating pressure, surface velocity, and PV is only part of the selection process. Those results still need to be compared with the ratings for the actual bearing. The frame calculation makes a similar point: a low direct stress does not replace a check of how the complete frame carries the load.

## Details Still to Verify

- Add the remaining eight handwritten screenshots and reconcile their inputs with this draft.
- Confirm belt geometry, material, strength, and friction assumptions.
- Confirm the shaft material supporting the assumed 85,000 psi yield strength.
- Confirm the bearing selection and its pressure, speed, PV, lubrication, and fit limits.
- Add the frame sketch and confirm its material, load path, and any needed bending or connection checks.

## Reference

[Pulley assignment structural reference](https://gracieanne14.github.io/design-projects-portfolio/assignments/A09/#lessons-learned)

The reference was used for section organization only. The numerical results above come from my handwritten screenshots, with arithmetic checked separately.
