<h1 align="center">
	PCB STANDARDS
	<br>
</h1>

<h4 align="center">Internal and external standards used in the SpaceLab hardware designs (PC-104, space design patterns, others).</h4>

<p align="center">
  	<a href="#overview">Overview</a> •
  	<a href="#pc-104-interface-specification">PC-104 interface specification</a> •
  	<a href="#pcb-design-for-space-applications">PCB design for space applications</a>
</p>


## Overview

These are the standards used in the SpaceLab hardware projects.

## PC-104 interface specification

To be defined!

## PCB design for space applications

Regarding the design guidelines, the rules specified in the ESA normative for printed circuit boards, [ECSS-Q-ST-70-12C](https://ecss.nl/standard/ecss-q-st-70-12c-design-rules-for-printed-circuit-boards-14-july-2014/), should be used as reference. In order to conciliate the board requirements for reliability and feasibility in terms of development time and funding, in the table bellow it is presented a summarized and simplified version of the main guidelines of this normative. In case of more critical designs, it is recommended to check the complete normative. 

| **Rules**                                                                                                                                                                                                                        |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| This is a mighty long text that could go over multiple lines but in a normal table is shown on one line and therefore the table does not fit on the page\.                                                                       |
| The copper thickness on both sides of a laminate must be the same, except in layers external plate\.                                                                                                                             |
| The outer and inner layers must use basic copper thickness of 70um, 35um or 17um\. This is necessary for the manufacturing process\.                                                                                             |
| The distribution of copper within a layer must be homogeneous\. This ensures homogeneous pressure during lamination, avoiding empty spaces, cracks or compression of the glass\. Mainly needed when using 70um thickness\.       |
| Tracks should not be routed in layers of copper plane\. This is done to avoid obstacles for the AF return currents\.                                                                                                             |
| The projected insulation distance between two layers must be at least 100um\. This avoids risk of reduced electrical insulation\.                                                                                                |
| The fabricated thickness of a rigid epoxy PCB must be less or equal to 2.4mm\.																																				   |
| The number of copper layers for an epoxy PCB must be less or equal to 20\.                                                                                                                                                       |
| The relationship between the thickness of the PCI and the diameter of the track hole on a rigid PCI must be less or equal to 7\.                                                                                                 |
| For copper thickness 17um, no width of track or track spacing and/or components must be less or equal to 96um, as considering manufacturing tolerances\.                                                                         |
| Tracks should not be routed in layers external\.                                                                                                                                                                                 |
| BGA component pads must be circular and with teardrop\.                                                                                                                                                                          |
| Minimum distance between BGA pads should be 1mm\.                                                                                                                                                                                |
| BGA component pads must be designed with track on the pad, be it micro track or track filled\.                                                                                                                                   |
| BGA footprint trails must be equidistant between the pads\. This increases the distance isolation\.                                                                                                                              |
| Pads must be designed with teardrop reinforcement\.                                                                                                                                                                              |
| Non\-functional pads should be kept on footprint\.                                                                                                                                                                               |
| Ring ring must be at least 50um wide in internal layers and 200um in external ones\.                                                                                                                                             |
| Copper planes larger than 10 cm²  must be made in grid format, with 45 degree rotation\. This creates ventilation openings and moisture evaporation of the inner layers\.                                                        |
| The fabricated thickness of a rigid epoxy HF PCB must be less or equal to 3mm\.                                                                                                                                                  |
| The number of copper layers for an epoxy PCB HF must be less or equal to 14\.                                                                                                                                                    |
| Dielectric strength of the material must be greater than 1000 Vrms/mm                                                                                                                                                            |
| For power distribution, a thickness of copper of 35um or more should be used\.                                                                                                                                                   |
| All conducting parts and standards must not be left isolated\.                                                                                                                                                                   |
| The temperature of the trails must be less than 85 degree celsius\.                                                                                                                                                              |
| Critical tracks should all be routed on one single layer\.                                                                                                                                                                       |
| Conductors in outer layers must be covered with polymeric film and not weld\.                                                                                                                                                    |
| Tracks with impedance control must be made in specific layers\.                                                                                                                                                                  |
| Paths should not be used on impedance tracks controlled, except for the connection with the components\.                                                                                                                         |
| Low\-speed digital circuits must be separate from high\-speed digital circuits\.                                                                                                                                                 |
| Grounding plans must be used in high\-speed digital applications\.                                                                                                                                                               |
| High speed signals must be routed above of uninterrupted power plans\.                                                                                                                                                           |
| The location of the components must be such that each solder connection can be visually inspected\.                                                                                                                              |
| The designed test points must be separated component pads\.                                                                                                                                                                      |
| The footprint fanout must be symmetrical\. This is done to prevent the component from moving in specific direction during the welding process\.                                                                                  |
| There must be a minimum distance of 0.25mm between the pads and the tracks\. This is done to prevent the solder removed from the pad by the route, in the welding\.                                                              |
| The width of a track must be less than 1/3 of the width of a pad\. This is done to prevent the trail remove heat from the pad during the welding process\.                                                                       |
