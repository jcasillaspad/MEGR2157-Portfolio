# A9 – Pulley Drive

## Objective

The objective of this assignment was to analyze a pulley drive, including the belt, shaft, journal bearings, and frame. I used a required safety factor of 3.

## Belt

I started with two 3 in pulleys, a 5 in center distance, a speed of 1,500 rpm, and an initial belt tension of 5 lbf. I assumed a tension ratio of 2 and a belt strength of 471 psi.

![Belt knowns and assumptions](IMG_0351.jpeg)

![Pulley free body diagram](IMG_0352.jpeg)

Using T1 + T2 = 2T0 and T1 = 2T2, I calculated tensions of 6.667 lbf and 3.333 lbf.

![Belt tension calculations](IMG_0353.jpeg)

The tension difference produces a torque of 5 in-lbf. Adding the tensions gives a 10 lbf load on the shaft.

![Torque and shaft load](IMG_0354.jpeg)

I calculated a minimum round belt diameter of 0.2325 in and selected 0.250 in. This gives a tensile stress of 135.8 psi and a safety factor of 3.47 using the assumed strength.

![Belt diameter and stress calculations](IMG_0356.jpeg)

![Belt safety factor](IMG_0357.jpeg)

Using the 3 in pulley diameter as the effective belt diameter, I calculated a belt path length of 19.425 in and a belt speed of 1,178.1 ft/min.

![Belt length and speed](IMG_0358.jpeg)

The transmitted power is approximately 0.119 hp.

![Power calculation](IMG_0359.jpeg)

For a wrap angle of 180 degrees, the minimum friction coefficient is approximately 0.221.

![Friction calculation](IMG_0360.jpeg)

## Shaft

I used the 5 in-lbf torque and assumed a shaft yield strength of 85,000 psi.

![Shaft knowns and torque diagram](IMG_0361.jpeg)

The torsion calculation gave a minimum diameter of 0.116 in. I selected a 0.375 in shaft.

![Minimum shaft diameter](IMG_0362.jpeg)

The torsional shear stress is approximately 483 psi, giving a torsion-only safety factor of 101.6.

![Shaft stress and safety factor](IMG_0363.jpeg)

I also included bending from the centered 10 lbf pulley load. With a 2 in bearing span, the maximum bending moment is 5 in-lbf. The combined bending and torsion stress is approximately 1,278 psi, giving a static yield safety factor of 66.5. This calculation is shown with the bearing PV calculation below.

## Journal Bearing

I used two bearings with a 0.375 in shaft diameter and a bearing length of 0.500 in. I placed the pulley load halfway between the supports.

![Bearing knowns and free body diagram](IMG_0364.jpeg)

Using force and moment equilibrium, I calculated a reaction of 5 lbf at each bearing.

![Bearing reactions](IMG_0365.jpeg)

The projected bearing area is 0.1875 in². This gives a bearing pressure of 26.67 psi and a surface velocity of 147.26 ft/min.

![Bearing pressure and velocity](IMG_0366.jpeg)

Multiplying pressure by velocity gives a PV value of approximately 3,927 psi-ft/min.

![Bearing PV and combined shaft stress](IMG_0367.jpeg)

## Frame

For the frame calculation, I used a 2 in wide, 0.250 in thick section carrying 5 lbf. I assumed a yield strength of 35,000 psi.

The cross-sectional area is 0.500 in², giving a direct stress of 10 psi. The allowable stress is 11,667 psi with a safety factor of 3. The calculated safety factor for this direct-stress model is 3,500.

![Frame stress calculation](IMG_0368.jpeg)

## Lessons Learned

The tension difference determines the transmitted torque, while the sum of the tensions determines the load on the shaft. Including bending also gives a lower shaft safety factor than checking torsion alone. The bearing calculations show how load, contact area, and speed affect pressure and PV.
