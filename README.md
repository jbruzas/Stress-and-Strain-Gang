# Hydraulic Robotic Arm
***Stress and Strain Gang***

<img width="1536" height="1024" alt="GPTSSG" src="https://github.com/user-attachments/assets/9ac9a32c-08a5-4b32-8829-c94b6ce13e38" />


*Jason Bruzas, Thomas Holtom, Zachary Miller, Anthony Nguyen, Diego Ordaz, Brennan Sweeten*


## Table of Contents
### [Phase 1](#phase-1-1)

[*Phase 1 Video*](#phase-1-video)

[*System description and functional overview*](#System-description-and-functional-overview) 

[*Component breakdown with labeled figures/sketches*](#component-breakdown-with-labeled-figuressketches)

[*Kinematic description and basic calculations*](#kinematic-description-and-basic-calculations)

[*Preliminary failure modes and design considerations*](#preliminary-failure-modes-and-design-considerations)

[*References for any external material (manuals, patents, data sheets, etc.)*](#references-for-any-external-material-manuals-patents-data-sheets-etc)

### Phase 2
*Phase 2 Video*

*Overview of your final design (with key CAD images)*

*Description of major design decisions and changes from Phase 1*

*Detailed explanation of required analyses (shaft, gear, fatigue, bearings, interfaces, etc.) with clear assumptions and results*

*Discussion of design for assembly and design for 3D printing*

*Updated list of anticipated risks or weaknesses to be addressed in prototyping*

### Phase 3
*Phase 3 Video*
*Fabrication details (filament type, printer, settings, number of reprints)*

*Assembly procedure and challenges*

*Test procedures, results, and interpretation*

*Comparison with Phase 2 predictions (where applicable)*

*Detailed discussion of failures, mistakes, and surprises*

*Concrete list of design changes you would implement in a second iteration*

## Phase 1
### Phase 1 Video

[![Phase 1 Video]
(https://img.youtube.com/vi/||/maxresdefault.jpg)]
(https://www.youtube.com/watch?v=||)

### System description and functional overview
Robotic arms have many uses in manufacuting and assembly. They are used for repetitive tasks like welding, sorting, or milling. These tasks are often done automatically. To be able to assist in or perform these tasks, the arm needs to pick up, maneuver, move, and hold items. For the purpose of this project, the robotic arm should be able to pick up and hold a 1 kilogram object, and will move via hydraulic power. The robotic arm will have three main segments, the base, the upper arm and forearm. The top two segments will have hydraulics attached to control the angles of each arm.

<img width="466" height="278" alt="image" src="https://github.com/user-attachments/assets/1cd4192c-d1b7-461b-8d68-6fb32ebeac1a" />

### Component breakdown with labeled figures/sketches
#### Claw

In the initial stages of sketching the design for the claw subsystem, the main issue that presented itself was the angle at which the hand-like component would grip an object in the main operating event. The initial design consisted of an angled grip system, allowing the claw to wrap the linkages around the side of an object. This was ultimately rejected due to the fundamental issue of objects slipping out before full closure. Instead, a more favorable design was considered with an ingenious solution: a two bar system that can allow the claw to open horizontally with the linear motion of a controlled hydraulic.

*Initial concept drawing of claw subsystem*

<img width="158" height="123" alt="image" src="https://github.com/user-attachments/assets/60a30817-5172-4971-b79d-60f5468b8f65" />

*Pre-design drawing of claw subsystem with two bar mechanism*

<img width="500" height="219" alt="image" src="https://github.com/user-attachments/assets/e1d2c6be-3ed8-449a-a4c3-74f8aa14c571" />

#### Hydraulic

The hydraulic subsystem is a key component for the hydraulic arm system to function. It must provide the capability for consistent extension and retraction in a linear direction for actuation of the arm member rotations. The hydraulic was modeled after standard fluid input/output hydraulics, and features the hydraulic barrel, fluid extension and retraction ports, piston, and piston rod as the main composition of the design chosen to perform the tasks needed for operating the hydraulic arm. In total, 3 hydraulic cylinders are necessary for the proper functions of the arm, including rotary motion in the main joints and claw subsystem.

*Pre-design drawing of hydraulic sub-system*

![Hydraulic System Drawing](https://github.com/user-attachments/assets/c069c980-c87d-4b6b-8714-37fba50fda19)

### Kinematic description and basic calculations
There will be two arm segments that can rotate indepentantly, giving the arm two degrees of freedom in the position of the claw.

![RoboticArmDesmosQuarterScale](https://github.com/user-attachments/assets/cd7bcf04-76a5-4b8e-a0b8-47239718c60c)

The position of the claw can be obtained from the lengths of the hydraulics using cosine law and trivial trigonometry relationships. However, determining appropriate hydraulic lengths based on desired claw position is a much more difficult task, requiring the inverse of the prior equations. This is difficult because isolating the hydraulic lengths requires rigorous application of trigonometric identities. These calculations are necessary for automatic robotic arms, but not for manual control, as the operator is able to adjust the hydraulics through trial and error. 

By assuming that system is undergoing quasi-static equilibrium and that the hydraulics only have axial forces going through them, it is possible to create a system of linear equations to solves for the forces on the fixed end at the bottom, forces on the two internal pins of the arm, and the internal force in the hydraulics. In conjunction with the kinematic calculations from earlier, one can predict the forces within the hydraulic arm when knowing the lengths of the members, the positions of the hydraulics, the mass of the system, the mass of the weight picked up by the claw, and the current lenght of the hydraulics. The Free Body diagrams from this calculation can be seen below: 

<img width="500" height="355" alt="Phase 1 - FBDs" src="https://github.com/user-attachments/assets/568e9665-c5a6-41dc-9ba4-6ab91015f2c8" />
Note: The variable names between the Kinematic and Statics calculations will vary as they were done by two separate people. 

From this analysis, it was determined that the bottom hydralic and the left-most pin experience the two highest forces out of any component, making these two components the most likely to fail due to static overload failure. 

### Preliminary failure modes and design considerations
The failure can happen at the pinned joints, for the cut-out of the holes in the beams can cause stress concentrations. Using the wrong pins or sizing can drastically affect the performance of the hydraulic arm. For example, a severe form of adhesive wear known as galling damage can cause the pins and bearings to tear due to high pressure and friction. Without proper maintenance, this can cause the hydraulic arm to stiffen until it can no longer move, effectively making the system useless. To ensure that this does not happen, a study conducted by Nader Farzaneh (in his thesis, Failure Analysis and Design of a Heavily Loaded Pin Joint) suggests that an undercut bushing will provide the longest longevity compared to other methods of pin jointing. Other ways to extend the life-time of the pins can be to lubricate the bearings and perform stress concentration calculations to determine where we will drill the hole as well as how large of a hole. Another area that needs to be considered is the motion of the beams. If one of the beams rotates too far, it can snap the hydraulics. To prevent this, we can put stoppers to limit the area of motion of each of the beams.

### Critical design parameters 
Before anything else within the hydraulic arm can be determined, the scale of the arm must be finalized. Any research into hydraulics, plastics, or pins would be worthless if the arm lengths change midway through the project. Thus, the arm lengths must be finalized before anything else can be done. Next is studying what plastic should be used as the material for the prototype. Material properties like density, Young’s modulus, and shear modulus will determine how much plastic can be used in the arm and what is the maximum force that the plastic can handle. The plastic also has to be 3D printed, so a 3D-printable plastic has to be chosen to fit this task as well. Then the hydraulics have to be chosen. Since there is likely no suitable way to design and 3D print a hydraulic, hydraulics will have to be scouted for online. Since the arm lengths and the plastic have been chosen already, the size of the hydraulics and the forces they have to exert will be well known. The hydraulics will be chosen based on the criteria of cost, maximum force it can exert, and size. Finally the pin design will be finalized. The arm lengths and type of plastic used will determine what forces the pins must be able to exert in order for the hydraulic arm to function. Thus, the type of pins used, the location of the pins, and the size of the pins will be determined in this step in order to minimize the amount of friction in the joint and to minimize the maximum force the pins must resist. 


### References for any external material (manuals, patents, data sheets, etc.)
https://www.nextengineers.org/sites/default/files/resources/hydraulic_robot_arm.pdf
https://hackaday.io/project/198164/logs
https://dspace.mit.edu/bitstream/handle/1721.1/89359/51805839-MIT.pdf?sequence=2#:~:text=At%20high%20loads%20and%20low,of%20the%20tests%20are%20presented.

