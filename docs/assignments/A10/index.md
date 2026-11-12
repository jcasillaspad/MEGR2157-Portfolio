# A10 – Lead Screw Translating System

## Objective
The objective of this assignment is to design a mechanically operated tensile testing system using two lead screws capable of applying a maximum axial tensile load of 2 kN with a controlled crosshead speed of 1–50 mm/min. The design process involves determining the appropriate lead screw diameter, rotational speed, and torque while maintaining a safety factor of 4. Additionally, the project includes selecting suitable nuts and flanges, designing a crosshead that meets strength and deflection requirements, and creating a complete CAD assembly in SolidWorks. The overall goal is to develop a safe, reliable, and accurate tensile testing system while applying engineering calculations, material selection, and mechanical design principles.


![Tensile Tester Design](Screenshot%202026-11-11%20at%2011.16.55%20PM.png)

![Tensile tester sketch](08-system-sketch.png)

## Lead Screw

**Diameter**

Since our design uses two identical lead screws, we assumed that each screw would carry half of the total 2,000 N load. We used a safety factor of 4 to make sure the screws would have enough strength to handle the load without yielding. After finding the minimum required diameter, we compared it to the size of the lead screw we selected. We chose a larger diameter to provide additional strength while still keeping the design practical.

![Lead screw diameter](01-diameter.png)

**Rotational Speed Range**

We used the lead of our selected screw, which was 2.54 mm per revolution, to calculate how fast the screws would need to rotate. The minimum required speed was approximately 0.39 RPM, and the maximum was 19.68 RPM. This showed us that the screws would need to rotate relatively slowly to produce the required crosshead movement. Both screws would also need to rotate at the same speed so the crosshead stays level while moving.

![Rotational speed](02-speed.png)

**Torque and Lead Screw Selection**

To calculate the torque, we used the inclined-plane method from class. This method helped us understand how the lead screw threads convert rotation into vertical movement. We assumed a friction coefficient of 0.15 between the screw and nut. Using this assumption, we calculated approximately 1.27 N*m of torque per screw, or 2.54 N*m for both screws before accounting for other mechanical losses.

We selected a 1/2"-10 carbon steel Acme lead screw from McMaster-Carr, part 98935A823. We chose this screw because its diameter was larger than the minimum we calculated, its length of 36 inches exceeded the 18-inch requirement, and its lead worked with our calculated rotational speed range.

![Torque calculations](03-torque-a.png)

![Torque and lead screw selection](03-torque-b.png)

## Nut and Flange

We selected a bronze flanged nut from McMaster-Carr, part 97790A110, to match our 1/2"-10 Acme lead screw. We chose a flanged nut because it could be attached to the crosshead using mounting holes. Each nut was assumed to carry 1,000 N of the total load.

We used the thread bending stress equation from class to estimate the minimum thread engagement length. Our preliminary calculation gave us a required length of 4.77 mm. We then used the selected bronze nut in our SolidWorks assembly and positioned one nut at each lead screw opening.

![Nut and flange calculations](04-nut-a.png)

![Nut engagement length](04-nut-b.png)

## Crosshead Design

**Stress Analysis**

We decided to use 6061-T6 aluminum for our crosshead because it has good strength while being relatively lightweight and easy to machine. We started with an overall length of 12 inches and a width of 4 inches. The width was chosen to provide enough space for the bronze flange nuts and their mounting holes.

For the calculations, we treated the crosshead as a simply supported beam with the load acting at the center. We used a 6-inch distance between the two lead screw locations. The bending stress calculation gave us a minimum height of approximately 8.08 mm, while the deflection calculation gave us approximately 13.63 mm.

![Crosshead stress calculations](05-strength-a.png)

![Crosshead thickness from stress](05-strength-b.png)

**Deflection Analysis**

Since deflection required a greater thickness than bending strength, we selected a final crosshead thickness of 20 mm. This gave us additional room for the mounting features while helping keep the crosshead stiff under the applied load.

![Crosshead deflection calculations](06-deflection-a.png)

![Selected crosshead thickness](06-deflection-b.png)

**Multiview Sketches**

We drew top, front, and side views of the crosshead to plan its shape before finishing the CAD model. These sketches show the overall dimensions, lead screw locations, center hole, and mounting hole layout.

![Crosshead sketches](07-sketches.png)

## CAD Assembly

We modeled the crosshead in SolidWorks and assembled it with the downloaded lead screws and flange nuts. We used mates to line up the screws with the crosshead holes and position the nuts against the crosshead.

![Lead screw assembly](Screenshot%202026-11-11%20204209.png)

After that, we added the vertical and horizontal frame pieces. We positioned these around the lead screw assembly to create the frame shown below.

![Frame assembly](Screenshot%202026-11-11%20220430.png)


## 2157 (FEA)

## Original Crosshead

**Load and Fixtures**

For the FEA, we used SolidWorks Simulation to test our crosshead under the required 2,000 N load. We selected 6061-T6 aluminum as the material because this was the material used in our original design calculations.

We applied the force at the center grip location to represent the pulling force on the crosshead. We also fixed the eight smaller mounting holes where the two bronze flange nuts attach to the crosshead. These locations were used to represent how the crosshead is supported by the lead screws.

![Applied load](Screenshot%202026-11-11%20221551.png)

**Mesh**

We generated a solid mesh for the crosshead so SolidWorks could calculate how the part would react to the applied force. The mesh divided the crosshead into smaller elements, including the areas around the mounting holes and the center grip location.

This allowed us to see where the highest stresses and displacements occurred.

![Crosshead mesh](Screenshot%202026-11-11%20221751.png)

**Original Crosshead Results**

After running the simulation, we looked at the von Mises stress and displacement results to see how the crosshead performed under the 2,000 N load.

The stress plot showed that most of the crosshead experienced relatively low stress. The higher stress areas appeared around the mounting holes and the center loading location. This helped us understand how the applied force was transferred through the crosshead to the supported ends.

![Original crosshead stress](Screenshot%202026-11-11%20222216.png)

We also looked at the resultant displacement to see how much the crosshead would bend under the load. The largest displacement occurred near the center of the crosshead, where the pulling force was applied.

The maximum resultant displacement was approximately 0.008731 mm, which was below the required limit of 0.1 mm. This showed that our original crosshead was stiff enough under the conditions used in the simulation.

![Original crosshead displacement](Screenshot%202026-11-11%20222153.png)

**Finer Mesh Results**

We ran another simulation using a finer mesh to see how the results changed when the elements became smaller.

With the finer mesh, the maximum von Mises stress was approximately 23.79 MPa, and the maximum resultant displacement was 0.008724 mm. The displacement was very close to our earlier result, which showed that the predicted bending changed very little between these two runs.

Using the aluminum yield strength of 276 MPa, the calculated factor of safety was approximately 11.60. This was greater than the required safety factor of 4.

![Fine mesh displacement](finemeshdisplacement.png)

**Modified Crosshead**

After reviewing the original simulation, we decided to make the crosshead lighter by removing material from areas that experienced relatively low stress.

We added two rectangular pockets near the opposite ends of the crosshead. Each pocket was cut 5 mm deep. We kept the center grip location and the mounting holes unchanged so the crosshead could still connect to the same components in our assembly.

![Optimized crosshead](Screenshot%202026-11-11%20223929.png)

We then compared the mass of the original crosshead with the modified design. The original crosshead weighed 1,702.42 grams, while the modified version weighed 1,652.80 grams.

This removed 49.62 grams of material, giving us a mass reduction of approximately 2.91%. Although the reduction was relatively small, it allowed us to make the crosshead lighter without changing its overall dimensions or mounting locations.

**Modified Crosshead FEA Results**

After modifying the geometry, we ran the static simulation again using the same material, applied load, and mounting constraints.

The modified crosshead had a maximum von Mises stress of approximately 22.40 MPa, which was slightly lower than the 23.79 MPa from our original finer-mesh simulation.

The calculated factor of safety increased from approximately 11.60 to 12.32. The higher stress areas were still concentrated around the mounting holes and center loading area.

![Optimized crosshead stress](optimizedstress.png)

The modified crosshead also had a maximum resultant displacement of approximately 0.008712 mm, compared to 0.008724 mm for the original finer-mesh design.

This showed that the modified crosshead maintained nearly the same stiffness while reducing its mass. Based on our simulation results, the modified crosshead remained below the maximum deflection limit of 0.1 mm and above the required safety factor of 4.


**Crosshead Drawing**

![Crosshead drawing](crossheaddrawing.png)

## Tabling Cost 

| Item # | Quantity | Name | Cost/Item | Total Cost | Purchase Link |
|---|---|---|---|---|---|
| 1 | 2 | Bronze Flanged Nut (97790A110) | $178.60 | $357.20 | [McMaster-Carr](https://www.mcmaster.com/97790A110) |
| 2 | 2 | Carbon Steel ACME Lead Screw (98935A823) | $9.90 | $19.80 | [McMaster-Carr](https://www.mcmaster.com/98935A823) |
| 3 | 4 | Aluminum T-Slot Frame (906T77) | $47.92 | $191.68 | [Grainger](https://www.grainger.com/product/80-20-T-Slot-Framing-System-Profiles-906T77) |
| | | ** Estimated Subtotal** | | **$568.68** | |

## Lessons Learned

Throughout this project, our team gained a better understanding of the engineering design process and how different mechanical components work together in a tensile testing machine. We learned how to select leadscrews based on axial stress, rotational speed, torque, and safety factors. We also learned the importance of selecting compatible components, such as the bronze flange nuts, and verifying that they can withstand the required loads.

One of the most important lessons was understanding how material selection and component dimensions affect the strength and stiffness of a design. When designing the crosshead, we applied bending stress and deflection equations to determine appropriate dimensions while ensuring that the component could support the 2 kN load. We also gained experience using SolidWorks to model components, create assemblies, and evaluate structural performance through finite element analysis (FEA).

Another important lesson was that engineering design requires adjustments and careful verification. Selecting a component based only on its dimensions is not sufficient; its material properties, load capacity, compatibility, and factor of safety must also be considered. Overall, this project improved our understanding of mechanical design, engineering calculations, CAD modeling, and the importance of documenting and justifying design decisions.

## CAD Download Files

[Click here to download lead_screw.SLDPRT](lead_screw.SLDPRT?raw=true)

[Click here to download flange_nut.SLDPRT](flange_nut.SLDPRT?raw=true)

[Click here to download frameheight.SLDPRT](frameheight.sldprt?raw=true)

[Click here to download framewidth.SLDPRT](framewidth.sldprt?raw=true)

[Click here to download Assembly.SLDASM](Assembly.SLDASM?raw=true)

[Click here to download crosshead.SLDPRT](crosshead.SLDPRT?raw=true)

[Click here to download crosshead.SLDDRW](crosshead.SLDDRW?raw=true)

[Click here to download crosshead_optimized.SLDPRT](crosshead_optimized.SLDPRT?raw=true)
