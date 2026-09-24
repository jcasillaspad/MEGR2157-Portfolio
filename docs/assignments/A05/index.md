# A5 – Bracket Design

## Objective

This assignment is to design a metal bracket that holds a polyester strap while the strap applies a horizontal force. The bracket fits onto a rigid T-shaped beam. The provided concept shows a round pin for the strap connected to a hanger below a T-shaped opening. The opening engages the rigid beam, so the force must travel from the pin through the bracket and into that support.

I need to determine the minimum dimensions of five bracket features, labeled A through E in the assignment. For each feature, the assignment requires a free body diagram and a strength calculation to prevent yielding, followed by a stiffness calculation to limit movement. I also need two separate paper multiview sketches, one based on stress and one based on stiffness, plus a reflection on the design choices and corrections. The calculation images below provide the detailed math; this page explains the design process and results.

![Bracket Concept Design](conceptdesign.png)

A is the strap pin, B is the hanger, C is the lower crossmember, D represents the side webs, and E represents the upper lips around the opening for the rigid support.

## Design Process

**Design Requirements**

I selected a 700 lbf force for each symmetric strap side within the assigned 500–800 lbf range. Under that load interpretation, the two sides apply 1,400 lbf to Feature A. I chose 6061-T6 aluminum and used a safety factor of 4. Each feature is limited to 0.005 in of deflection; the preliminary calculations use a 40 ksi yield strength and 10 Msi elastic modulus.

The concept image has no scale, so I assumed the working lengths and 0.75 in section depth shown in the calculation screenshots. The T-beam opening and fit dimensions a, b, and c still need to be measured before these sketches can serve as fabrication drawings.

## Stress Analysis

**Feature A**

The strap loads the cylindrical pin along its length. The screenshot records the applied load, support reaction, stress model, and minimum stress dimension.

![Feature A Stress Analysis](stressa.jpeg)

**Feature B**

I carried A’s support reaction into the vertical hanger and modeled its rectangular section in axial loading. The screenshot records the applied load, support reaction, stress model, and minimum stress dimension.

![Feature B Stress Analysis](stressb.jpeg)

**Feature C**

I applied B’s load at the center of the lower beam. The screenshot records the applied load, support reaction, stress model, and minimum stress dimension.

![Feature C Stress Analysis](stressc.jpeg)

**Feature D**

Each side web receives one reaction from C. The screenshot records the applied load, support reaction, stress model, and minimum stress dimension.

![Feature D Stress Analysis](stressd.jpeg)

**Feature E**

I treated each upper lip as a short cantilever carrying the reaction passed through D. The screenshot records the applied load, support reaction, stress model, and minimum stress dimension.

![Feature E Stress Analysis](stresse.jpeg)

## Stiffness Analysis

**Feature A**

I repeated the same force path using a 0.005 in deflection limit for each feature. The beam checks use bending deflection, while the axial members use elongation.

I used the same load and assumed span as the stress analysis, then solved for the minimum section dimension that meets the deflection limit.

![Feature A Stiffness Analysis](stiffnessa.jpeg)

**Feature B**

I used the same load and assumed span as the stress analysis, then solved for the minimum section dimension that meets the deflection limit.

![Feature B Stiffness Analysis](stiffnessb.jpeg)

**Feature C**

I used the same load and assumed span as the stress analysis, then solved for the minimum section dimension that meets the deflection limit.

![Feature C Stiffness Analysis](stiffnessc.jpeg)

**Feature D**

I used the same load and assumed span as the stress analysis, then solved for the minimum section dimension that meets the deflection limit.

![Feature D Stiffness Analysis](stiffnessd.jpeg)

**Feature E**

I used the same load and assumed span as the stress analysis, then solved for the minimum section dimension that meets the deflection limit.

![Feature E Stiffness Analysis](stiffnesse.jpeg)

## Multiview Sketches

**Multiview Sketches**

Here are my multi view sketches for both stress and stiffness analysis

![Stress Multiview Sketch](multiviewstress.jpeg)

![Stiffness Multiview Sketch](multiviewstiffness.jpeg)

## Link Design

**Link Dimensions**

I used 6061-T6 aluminum and a 1,400 lbf load from the two 700 lbf strap forces. I assumed a 1.75 in link width and 2.50 in spacing between holes. The 1-inch hole leaves the smallest cross-section, so I used it to size the link. Stress required a 0.187 in thickness and stiffness required 0.093 in, so I chose 0.250 in. At that thickness, the link’s elongation is 0.00187 in, below the 0.005 in limit.

![Thickness Calculations](thickness.jpeg)

**Fit at Feature A**

I chose an RC2 sliding fit for the Ø0.900 in pin. The link hole is 0.9000–0.9005 in diameter, and the pin is 0.8993–0.8997 in diameter. I would finish the hole by reaming or boring and turn the pin to size. I used Machinery’s Handbook, 31st ed., Table 8a, pp. 654–655, and the machining-process table on p. 649.

![Table 8a 1](8aa.png)

![Table 8a 2](8ab.png)

**Fit at Shaft**

I chose an FN1 light drive fit, which uses light pressure to assemble. The link hole is Ø1.0000–1.0005 in, and the shaft is Ø1.0008–1.0012 in. I would finish-bore the hole, turn or grind the shaft, and press them together. I used Machinery’s Handbook, 31st ed., Table 11, pp. 664–665, and the machining-process table on p. 649.

![Table 11 1](11a.png)

![Table 11 1](11b.png)


## Lessons Learned

**Governing Requirement**

For Feature C, stress required 0.837 in while stiffness required 0.526 in, a 0.311 in difference. The larger stress dimension sets the preliminary height.

**Error Propagation**

C’s two 700 lbf reactions become the D and E loads. Using 700 lbf instead of 1,400 lbf at C would incorrectly halve both of those reactions and undersize the later features.

**Assumption Sensitivity**

The beam deflection terms depend strongly on unsupported length. If the actual C span is longer than the assumed 2.50 in, its stiffness requirement rises; I must update the span and recalculate before using the dimensions in a finished design.
