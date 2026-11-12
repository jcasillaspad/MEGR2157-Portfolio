# A10 – Lead Screw Translating System

## Objective
The objective of this assignment is to design a mechanically operated tensile testing system using two lead screws capable of applying a maximum axial tensile load of 2 kN with a controlled crosshead speed of 1–50 mm/min. The design process involves determining the appropriate lead screw diameter, rotational speed, and torque while maintaining a safety factor of 4. Additionally, the project includes selecting suitable nuts and flanges, designing a crosshead that meets strength and deflection requirements, and creating a complete CAD assembly in SolidWorks. The overall goal is to develop a safe, reliable, and accurate tensile testing system while applying engineering calculations, material selection, and mechanical design principles.


![Tensile Tester Design](Screenshot%202026-11-11%20at%2011.16.55%20PM.png)

![Tensile tester sketch](08-system-sketch.png)

## Lead Screw

![Lead screw diameter](01-diameter.png)

![Rotational speed](02-speed.png)

![Torque calculations](03-torque-a.png)

![Torque and lead screw selection](03-torque-b.png)

## Nut and Flange

![Nut and flange calculations](04-nut-a.png)

![Nut engagement length](04-nut-b.png)

## Crosshead Design

**Stress Analysis**

![Crosshead stress calculations](05-strength-a.png)

![Crosshead thickness from stress](05-strength-b.png)

**Deflection Analysis**

![Crosshead deflection calculations](06-deflection-a.png)

![Selected crosshead thickness](06-deflection-b.png)

**Multiview Sketches**

![Crosshead sketches](07-sketches.png)

## CAD Assembly

![Lead screw assembly](Screenshot%202026-11-11%20204209.png)

![Frame assembly](Screenshot%202026-11-11%20220430.png)

## 2157 (FEA)

**Original Crosshead**

![Applied load](Screenshot%202026-11-11%20221551.png)

![Crosshead mesh](Screenshot%202026-11-11%20221751.png)

![Original crosshead stress](Screenshot%202026-11-11%20222216.png)

![Original crosshead displacement](Screenshot%202026-11-11%20222153.png)

![Fine mesh displacement](finemeshdisplacement.png)

**Modified Crosshead**

![Optimized crosshead](Screenshot%202026-11-11%20223929.png)

![Optimized crosshead stress](optimizedstress.png)

## Lessons Learned

Throughout this project, our team gained a better understanding of the engineering design process and how different mechanical components work together in a tensile testing machine. We learned how to select leadscrews based on axial stress, rotational speed, torque, and safety factors. We also learned the importance of selecting compatible components, such as the bronze flange nuts, and verifying that they can withstand the required loads.

One of the most important lessons was understanding how material selection and component dimensions affect the strength and stiffness of a design. When designing the crosshead, we applied bending stress and deflection equations to determine appropriate dimensions while ensuring that the component could support the 2 kN load. We also gained experience using SolidWorks to model components, create assemblies, and evaluate structural performance through finite element analysis (FEA).

Another important lesson was that engineering design requires adjustments and careful verification. Selecting a component based only on its dimensions is not sufficient; its material properties, load capacity, compatibility, and factor of safety must also be considered. Overall, this project improved our understanding of mechanical design, engineering calculations, CAD modeling, and the importance of documenting and justifying design decisions.

## Decide

## Communicate

[Click here to download lead_screw.SLDPRT](lead_screw.SLDPRT?raw=true)

[Click here to download flange_nut.SLDPRT](flange_nut.SLDPRT?raw=true)

[Click here to download frameheight.SLDPRT](frameheight.sldprt?raw=true)

[Click here to download framewidth.SLDPRT](framewidth.sldprt?raw=true)

[Click here to download Assembly.SLDASM](Assembly.SLDASM?raw=true)

[Click here to download crosshead.SLDPRT](crosshead.SLDPRT?raw=true)

[Click here to download crosshead.SLDDRW](crosshead.SLDDRW?raw=true)

[Click here to download crosshead_optimized.SLDPRT](crosshead_optimized.SLDPRT?raw=true)
