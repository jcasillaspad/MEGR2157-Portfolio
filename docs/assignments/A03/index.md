# A3 – Parametric and FEA

## Objective
For this assignment I was tasked with designing a beam with a circular cross-sectional area and use two types of analysis: axial deformation and finite element analysis. The beam was to be designed of aluminum and subjected to a force between 300 and 500 lbf with a maximum deflection of 0.009 inches. The Young's Modulus of the beam had to fit within the range of (8.5 - 11.5) *10^6 psi.


## Parametric Design
**Beginning Design**
I began the design process by selecting the geometry of the beam. I chose the beam to have a diameter of 0.70 inches. I also chose 420 lbf as my force to be applied to the end of the beam, and a Young's Modulus of 10x10^6.

![Beam Drawing](beamdrawing.jpeg)

After choosing the geometry and parameters of the beam, I calculated the cross-sectional area to be 0.3848 inches^2 by using the area formula for a circle (pi x d^2)/4. Then, using the direct tension elongation equation and moving it around to solve for length, I found the length of the beam, with a 0.70 inch diameter, to be 82.46 inches.

![Beam Calculations](beamcalculations.jpeg)

**CAD Design**
To make my model and conduct a FEA I decided to use Solidworks. I began making my model by assigning all of my parameters to parametric equations.

![Parameters](parameters.png)

Then I made a circle sketch on the front place using the diameter parameter and extruded using the length parameter equation.

![Sketch](sketch.png)
![Extrude](extrude.png)
![Model](model.png)

## FEA
**FEA Setup**
To conduct a FEA I added the 420 lbf to one face of the beam and on the opposite face I added a fixed geometry to represent a fixed support.

![FEA Setup](feasetup.png)

I also needed to add a material to perform a FEA; however, when I looked through the Solidworks materials I did not see an aluminum with a modulus of 10x10^6 that I had chosen for my calculations. To combat this issue I created a custom aluminum material with a Young's Modulus of 10x10^6 psi, and a Poisson's Ratio of 0.33 which I found was common for aluminum materials, and using those two values I calculated the Shear Modulus to be 3.76x10^6 psi. All of these values were needed to make the custom material.

![Material Properties](materialproperties.jpeg)
![Custom Material](custommaterial.png)

**FEA Results**
Then I conducted a FEA and generated the deflection map.

![FEA Displacement](feadisplacement.png)

I also generated the Von Mises Stress map.

![FEA Stress](feastress.png)

## Decide


## Communicate

