# A6 – Parametric Bracket Design and Drawing

## Objective

The objective of this assignment is to turn the bracket design from [Assignment 5](../A05/index.md) into a parametric solid model and a multiview engineering drawing in SolidWorks. The bracket fits over a rigid T-shaped beam and supports the polyester strap through a cylindrical pin. This page documents the bracket modeling process and the current drawing. The separate link will be documented later.

## Design Process

**Design Inputs**

I carried forward the 700 lbf load on each strap side, giving a total load of 1,400 lbf, and the selected 6061-T6 aluminum from Assignment 5. The preliminary analysis used a safety factor of 4, a yield strength of 40,000 psi, an elastic modulus of 10,000,000 psi, and a 0.005 in deflection limit for each feature.

The revised T-beam specification gives a = 0.498 in, b = 0.9992 in, and c = 1.499 in. For the symmetric cross-section, the nominal overall beam width is a + 2b = 2.4964 in. I used a 0.5020 in top slot, a 2.5024 in lower cavity width, and a 1.5050 in cavity height as preliminary opening dimensions. These model dimensions provide nominal clearance, but the three sliding-fit tolerances still need to be finalized on the drawing.

## Parametric Equations

**Global Variables**

I entered the dimensions as global variables so the sketches and extrusions could refer to named dimensions rather than separately entered values. The screenshot shows the parameter table and the analytical expression for the crossmember.

![SolidWorks bracket global variables and crossmember equation](globalvariables.png)

**Equation Driving Feature C**

The total load P is 1,400 lbf, the assumed support span L is 2.6024 in, the section depth w is 0.750 in, and the allowable stress is 40,000 / 4 = 10,000 psi. The support span is the cavity width plus one web thickness, representing the distance between web centerlines.

I entered the equation directly in SolidWorks and added a 0.020 in design allowance:

**"Crossmember_height" = (3 * 1400 * 2.6024 / (2 * 0.75 * 10000)) ^ (1 / 2) * 1in + 0.020in**

The equation evaluates to approximately 0.8736 in and controls the material below the T opening. The main body height also references this parameter, so the body height depends on the calculated crossmember height.

The original 2.50 in span in Assignment 5 gave a strength minimum of approximately 0.837 in. With the revised 2.6024 in span, the minimum increases to approximately 0.8536 in before the design allowance.

The expression currently contains the load and span as numerical constants. If the cavity width or web thickness changes, the 2.6024 in span must be updated manually in this expression. The sketches that reference Crossmember_height are set up to follow its result; a separate before-and-after rebuild test has not yet been documented.

## CAD Modeling

**Main Body Sketch and Extrusion**

I started on the Front Plane with a rectangular body sketch and positioned the midpoint of its bottom edge at the origin. This placed the origin at the body underside, which later became the reference for the hanger and pin.

The width was defined as T_cavity_width + 2 × Web_thickness. The height was defined as Crossmember_height + T_cavity_height + Lip_height. These relationships give an approximate body width of 2.7024 in and height of 3.1486 in.

![Parametric main body rectangle](bodysketch.png)

I extruded this sketch to the 0.750 in Bracket_depth.

**Lower T Cavity**

On the body face, I sketched the wide rectangular opening and centered it about a vertical construction line. I controlled its width with T_cavity_width and its height with T_cavity_height. The distance from the body bottom to the cavity bottom was tied to Crossmember_height.

![Lower cavity sketch and crossmember height](cavitysketch.png)

I used a Through All cut to create the lower opening. This left the lower crossmember and the two side webs.

**Top Slot**

I added a centered rectangle connecting the upper edge of the lower cavity to the top of the body. Its width was controlled by Top_slot_width.

![Centered top slot sketch](topslotsketch.png)

I cut this sketch Through All so the T-shaped opening continued through the full body depth.

**Rear Hanger**

I sketched the hanger on the rear face of the body, centered it horizontally, and placed its top edge at the body underside. The width was controlled by Hanger_width. The full rectangular hanger height was Hanger_length + Pin_diameter / 2, or approximately 1.44975 in.

![Rear hanger sketch](hangersketch.png)

I extruded the hanger 0.200 in toward the front of the bracket with Merge result enabled. This placed the hanger at the rear of the body.

**Pin Sketch and Extrusion**

On the rear hanger face, I sketched the pin circle and aligned its center vertically with the origin. I positioned its center 1.000 in below the main body underside and set the diameter to Pin_diameter = 0.8995 in.

![Corrected pin sketch and center location](pinsketch.png)

I extruded the pin toward the front by Pin_free_length + Hanger_thickness = 1.200 in, with Merge result enabled. This creates 1.000 in of exposed pin beyond the hanger's front surface.

**Bracket Model**

The current solid model includes the T opening, lower crossmember, side webs, upper lips, rear hanger, and cylindrical pin.

![Isometric bracket solid model](bracketmodel.png)

## Engineering Drawing

**Multiview Layout**

I created a drawing with a front view, a top view above it, a right-side view to its right, and an isometric view for orientation. This arrangement follows a third-angle projection layout. The current sheet uses a 1:2 scale and identifies the part as Bracket.

![Current bracket engineering drawing](bracketdrawing.png)

The drawing currently shows dimensions for the body, side web, lip overhang, pin, hanger, and overall height. Its dimensions are displayed at limited precision, so the image should not be interpreted as the final specification of the fit surfaces.

## Mistakes and Corrections

**Equation Syntax**

The first Crossmember_height expression produced a syntax error in SolidWorks. I simplified the expression and entered the global-variable name separately from its Value/Equation entry. The current parameter table shows the expression evaluating to approximately 0.87 in at the displayed precision.

**Pin Location Reference**

I initially dimensioned the circle center 1.000 in below the hanger's bottom edge. This placed the pin circle below the hanger. I removed that dimension and measured from the main body underside at the origin instead. The corrected sketch places the pin center 1.000 in below the body, overlapping the hanger for the boss extrusion.

**Lip Dimension Correction**

The handwritten 0.50 in lip selection in Assignment 5 was below its calculated 0.648 in strength minimum. The revised T-beam geometry increased the assumed overhang further. I used a 0.770 in lip height for the current model rather than carrying the 0.50 in selection into CAD.

## Lessons Learned

**References Communicate Design Intent**

The pin-location error showed that a dimension needs both a value and the correct reference. A 1.000 in distance from the hanger bottom placed the pin outside the intended attachment region, while the same distance from the body underside produced the intended position.

**Analytical Dimensions and Geometric Relationships**

The crossmember equation places the strength calculation directly in CAD. Referencing its result in the cavity location and overall body height connects the analytical dimension to the solid geometry. However, the numerical span inside the equation does not update by itself when the cavity changes; that input still requires manual editing.

**Updated Specifications Affect More Than the Opening**

Changing the T-beam specification affects the opening width, the crossmember support span, and the upper-lip overhang. These changes can alter the required structural dimensions, so replacing only the opening dimensions would leave parts of the earlier analysis out of date.

**Model Precision and Drawing Precision**

The parameter table and sketches round displayed values. A displayed diameter of 0.90 in does not communicate the pin's 0.8993–0.8997 in fit limits. The drawing must specify those limits explicitly. Applying an unnecessarily tight tolerance to a non-critical exterior feature can increase machining and inspection effort without improving the bracket's function.

## Time Spent

I have spent approximately **3 hours** on the bracket modeling and drawing so far. This is the current total, not the final start-to-finish time for Assignment 6.

## CAD Download Files

The native bracket part, drawing, and drawing PDF have not yet been uploaded to this assignment page. Download links will be added when those files are available. The screenshot above documents the current drawing; it does not replace a downloadable CAD file or the required final PDF.
