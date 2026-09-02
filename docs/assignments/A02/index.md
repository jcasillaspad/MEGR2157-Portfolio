# A2 – Truss Stress Analysis

## Objective
The objective of this assignment was to design a lightweight planar truss capable of supporting the specified loads while maintaining the required factors of safety.

![Given Constraints](constraints.png)

I designed a simple four-joint, five-member truss using members AB, BC, CD, AD, and BD, with a pin support at A and a roller support at B. The truss members were designed using A500 structural steel.

For this design, I selected an applied load of P = 25 kN, which is within the required range of 20–30 kN. The given geometric dimensions were a = 0.4 m and b = 0.3 m. A500 Structural steel has a specified minimum yield strength of 50 ksi and minimum tensile strength of 62 ksi.

## Analyze
**Truss Geometry**
I selected a five-member truss consisting of members AB, BC, CD, AD, and BD.

![Drawn Truss Geometry](constraints.png)

The geometry creates two triangular regions, BCD and BAD. This is useful because triangles provide geometric stability without requiring unnecessary additional members.

**Member Lengths**
The lengths of each member can be found using simple geometry.

![Shown Member Geometry](constraints.png)

**Truss Free-Body Diagram**
The pin at A can produce horizontal and vertical reactions, while the roller at B produces only a vertical reaction. For the FBD, only the entire truss and these five external forces need to be drawn. This is to show the overall FBD of the truss without showing the internal member forces.

![Overall FBD](constraints.png)

I found the support reactions using basic equilibrium equations and moment about point B.

![Support Reactions](constraints.png)

**Joint Analysis**
For the method of joints, I assumed every unknown member force was initially in tension, meaning the force arrows point away from the joint. A positive answer therefore represents tension and a negative answer represents compression.

![Joint C FBD](constraints.png)

![Joint A FBD](constraints.png)

![Joint D FBD](constraints.png)

I found the internal forces to be:
AB = -11.11 kN (Compression)
BC = -41.67 kN (Compression)
CD = -33.33 kN (Compression)
AD = +13.89 kN (Tension)
BD = +47.47 kN (Tension)
With this information, I concluded that Fmax = 47.47 kN.

**Member Cross-Section Design**
It is known that Fmax = 47.47 kN, the factor of safety, N = 3.5, and for A500 structured steel Fy = 50 ksi = 344.73 MPa; this is the minimum yield strength for A500 structured steel. The unknown is the minimum area.

![Area Calculation](constraints.png)

With that information, I was able to find the minimum area required to be 481.91 mm^2.

**Approximate Truss Weight**

![Truss Weight](constraints.png)

I was able to determine the theoretical weight of the truss members to be 13.07 kg.

**Pin Design**

## Decide
_Which geometry did you select, and why? This is your first open design choice in the course — defend it._

## Communicate

