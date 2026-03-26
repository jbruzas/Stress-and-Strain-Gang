# Hydraulic Robotic Arm
***Stress and Strain Gang***

<img width="1536" height="1024" alt="GPTSSG" src="https://github.com/user-attachments/assets/9ac9a32c-08a5-4b32-8829-c94b6ce13e38" />


*Jason Bruzas, Thomas Holtom, Zachary Miller, Anthony Nguyen, Diego Ordaz, Brennan Sweeten*


## Table of Contents
### [Phase 1](#phase-1-1)

[*Phase 1 Video*](#phase-1-video)

[*Executive Summary*](#executive-summary)

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

*Discussion of design for assembly*

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

[![Phase 1 Video](figures/Phase1Thumbnail.png)](https://www.youtube.com/watch?v=qbWg8F8cuA8)

### Executive Summary 
The purpose of the phase 1 report includes the system functionality and components, kinematic calculations, preliminary failure mode review, critical design parameters, and a YouTube video that summarizes the project. 

The groups are tasked with choosing a mechanical system to design, model, and test. This is meant for students to apply their knowledge of mechanical engineering that they have learned up to this point to a real project. This both allows students to get some experience of how engineering is done in the real world and allows them to better understand the engineering concepts that go into making their designs. This mechanical system must be suitably complex so that every single group member is able to contribute but simple enough that each phase of the project can be completed on time. 

The mechanical system chosen to be studied was that of a hydraulic arm. The use of hydraulics is a cornerstone of many civil engineering and robotics projects, so understanding them is of key importance to mechanical engineers. The hydraulic arm chosen has 2 degrees of freedom because it has two hydraulics that control the position of the arm. These two degrees of freedom make the hydraulic arm suitably complex enough that CAD software and a lot of manpower is needed to fully understand the kinematics and statics of the arm. Thus, a hydraulic arm is excellent for fulfilling the criteria of the project being suitably complex; here, each group member contributes, and it teaches how to apply hydraulics to a real engineering problem. 

The plan after the phase 1 report is completed is to immediately start creating CAD models of the hydraulic arm so the design process can begin. From this, the specification of each component can be fully identified, and the kinematics and statics of the CAD models can be analyzed using FEM to see if the ideas work in theory. The CAD models will be designed in Solidworks or Ansys, with the FEM being handled by Ansys. 

### System description and functional overview
Robotic arms have many uses in manufacturing and assembly. They are used for repetitive tasks like welding, sorting, or milling. These tasks are often done automatically. To be able to assist in or perform these tasks, the arm needs to pick up, maneuver, move, and hold items. For the purpose of this project, the robotic arm should be able to pick up and hold a 1-kilogram object and will move via hydraulic power. The robotic arm will have three main segments: the base, the upper arm, and the forearm. The top two segments will have hydraulics attached to control the angles of each arm.

<img width="466" height="278" alt="image" src="https://github.com/user-attachments/assets/1cd4192c-d1b7-461b-8d68-6fb32ebeac1a" />

### Component breakdown with labeled figures/sketches
#### Claw

In the initial stages of sketching the design for the claw subsystem, the main issue that presented itself was the angle at which the hand-like component would grip an object in the main operating event. The initial design consisted of an angled grip system, allowing the claw to wrap the linkages around the side of an object. This was ultimately rejected due to the fundamental issue of objects slipping out before full closure. Instead, a more favorable design was considered with an ingenious solution: a two-bar system that can allow the claw to open horizontally with the linear motion of a controlled hydraulic.

*Initial concept drawing of claw subsystem*

<img width="158" height="123" alt="image" src="https://github.com/user-attachments/assets/60a30817-5172-4971-b79d-60f5468b8f65" />

*Pre-design drawing of claw subsystem with two-bar mechanism*

<img width="500" height="219" alt="image" src="https://github.com/user-attachments/assets/e1d2c6be-3ed8-449a-a4c3-74f8aa14c571" />

#### Hydraulic

The hydraulic subsystem is a key component for the hydraulic arm system to function. It must provide the capability for consistent extension and retraction in a linear direction for actuation of the arm member rotations. The hydraulic was modeled after standard fluid input/output hydraulics and features the hydraulic barrel, fluid extension and retraction ports, piston, and piston rod as the main composition of the design chosen to perform the tasks needed for operating the hydraulic arm. In total, 3 hydraulic cylinders are necessary for the proper functions of the arm, including rotary motion in the main joints and claw subsystem.

*Pre-design drawing of hydraulic subsystem*

![Hydraulic System Drawing](https://github.com/user-attachments/assets/c069c980-c87d-4b6b-8714-37fba50fda19)

### Kinematic description and basic calculations
There will be two arm segments that can rotate independently, giving the arm two degrees of freedom in the position of the claw.

![RoboticArmDesmosQuarterScale](https://github.com/user-attachments/assets/cd7bcf04-76a5-4b8e-a0b8-47239718c60c)
<img width="265" height="262" alt="AngleCalcs" src="https://github.com/user-attachments/assets/09fae91d-21a5-423d-abcb-42df611f85e8" />
<img width="722" height="578" alt="ParameterLabels" src="https://github.com/user-attachments/assets/da28e28a-7660-40e7-9073-c282fefc4517" />


The position of the claw can be obtained from the lengths of the hydraulics using cosine law and trivial trigonometry relationships. However, determining appropriate hydraulic lengths based on desired claw position is a much more difficult task, requiring the inverse of the prior equations. This is difficult because isolating the hydraulic lengths requires rigorous application of trigonometric identities. These calculations are necessary for automatic robotic arms, but not for manual control, as the operator is able to adjust the hydraulics through trial and error. 

By assuming that the system is undergoing quasi-static equilibrium and that the hydraulics only have axial forces going through them, it is possible to create a system of linear equations to solve for the forces on the fixed end at the bottom, the forces on the two internal pins of the arm, and the internal force in the hydraulics. In conjunction with the kinematic calculations from earlier, one can predict the forces within the hydraulic arm when knowing the lengths of the members, the positions of the hydraulics, the mass of the system, the mass of the weight picked up by the claw, and the current length of the hydraulics. The Free Body diagrams from this calculation can be seen below: 

<img width="500" height="355" alt="Phase 1 - FBDs" src="https://github.com/user-attachments/assets/568e9665-c5a6-41dc-9ba4-6ab91015f2c8" />

Note: The variable names between the Kinematic and Statics calculations will vary as they were done by two separate people. 

After getting the linear system of equations from the statics calculations, MATLAB was used to solve the system by substituting in reasonable values for each of the unknown constants. From this analysis, it was determined that the bottom hydraulic and the left-most pin experience the two highest forces out of any component, making these two components the most likely to fail due to static overload failure. The statics caluation work and the MATLAB code can be accessed below. 

Statics Calculation work: https://drive.google.com/file/d/1Ut7OGnmQNidH3Am7ShedRqDdGQ3p2LGb/view?usp=sharing

MATLAB Code: https://drive.google.com/file/d/1DJdaTfVr9Ji7mV_dZBP7UAXajvhnQ-qj/view?usp=sharing

### Preliminary failure modes and design considerations
The failure can happen at the pinned joints, for the cut-out of the holes in the beams can cause stress concentrations. Using the wrong pins or sizing can drastically affect the performance of the hydraulic arm. For example, a severe form of adhesive wear known as galling damage can cause the pins and bearings to tear due to high pressure and friction, causing wear failure. Without proper maintenance, this can cause the hydraulic arm to stiffen until it can no longer move, effectively making the system useless. What's worse is that the left-most pin also experiences a large amount of force as seen from the statics calculations, so the friction issue will also make static overload failure more likely. 

To ensure that this does not happen, a study conducted by Nader Farzaneh (in his thesis, Failure Analysis and Design of a Heavily Loaded Pin Joint) suggests that an undercut bushing will provide the longest longevity compared to other methods of pin jointing. Other ways to extend the life-time of the pins can be to lubricate the bearings and perform stress concentration calculations to determine where we will drill the hole as well as how large of a hole. Another area that needs to be considered is the motion of the beams. If one of the beams rotates too far, it can snap the hydraulics. Hydraulics are terrible at resisting shear stresses, so they can easily fail due to static overload failure if too much shear force is present. To prevent this, we can put stoppers to limit the area of motion of each of the beams, which minimizs the possible shear forces on the hydraulics.

### Critical design parameters 
Before anything else within the hydraulic arm can be determined, the scale of the arm must be finalized. Any research into hydraulics, plastics, or pins would be worthless if the arm lengths change midway through the project. Thus, the arm lengths must be finalized before anything else can be done. Next is studying what plastic should be used as the material for the prototype. Material properties like density, Young’s modulus, and shear modulus will determine how much plastic can be used in the arm and what is the maximum force that the plastic can handle. The plastic also has to be 3D printed, so a 3D-printable plastic has to be chosen to fit this task as well. 

Since there is likely no suitable way to design and 3D print a hydraulic, hydraulics will have to be scouted for online. Since the arm lengths and the plastic have been chosen already, the size of the hydraulics and the forces they have to exert will be well known. The hydraulics will be chosen based on the criteria of cost, maximum force it can exert, and size. Finally the pin design will be finalized. The arm lengths and type of plastic used will determine what forces the pins must be able to exert in order for the hydraulic arm to function. Thus, the type of pins used, the location of the pins, and the size of the pins will be determined in this step in order to minimize the amount of friction in the joint and to minimize the maximum force the pins must resist. 

### References for any external material (manuals, patents, data sheets, etc.)
https://www.nextengineers.org/sites/default/files/resources/hydraulic_robot_arm.pdf
https://hackaday.io/project/198164/logs
https://dspace.mit.edu/bitstream/handle/1721.1/89359/51805839-MIT.pdf?sequence=2#:~:text=At%20high%20loads%20and%20low,of%20the%20tests%20are%20presented.

## Phase 2 
### Phase 2 Video

### Overview of the Final Design
A hydraulic arm was created using SolidWorks and ANSYS. The choice of using two different softwares comes from the different analyses that both of these softwares can do. With SolidWorks, it can do simple FEA calculations, and its software allows ease of creating components and assembling the components together. On the other hand, ANSYS can do complex FEA calculations and provide a more detailed analysis on how the structure reacts under stress. With both of these softwares in mind, the decision came down to assembling and analyzing the full hydraulic arm in SolidWorks, and then do a more in-depth analysis on each of the components using ANSYS. Images of the assembly isometric view, the assembly exploded view, and each of the components can be found below: 

Assembly Isometric View: 

Assembly Exploded View: 

Claw: 

Hydraulic: 

Base: 

Middle Arm: 

Upper Arm:

### Major Design Decisions and Changes

The main design consideration was nailing what the actual scale of the final design should be. This hydraulic arm is intended to be used in a factory or industrial setting to grab objects and boxes from around a meter away. It was reasoned that the arm should be able to pick up objects that are maximum around 200 kg in mass, or around 1962 N in weight. The material of the arm was decided to be an aluminum alloy, specifically the general "aluminum alloy" in ANSYS and 6061 aluminum alloy in SOLIDWORKS. This was done to make the arm cost effective while still being reasonably strong.

The length of the upper and middle arms together should be 20% longer than the intended maximum reach, or around 1.2 m. At the start of phase 1, it was assumed that the two arms were going to be roughly the same length just to make constructing the inital CAD model easier. However, analyzing the system in both SOLIDWORKS and ANSYS determined that the upper arm needs to be shorter than the middle arm. This is due to the fact that there are significant bending stresses in the middle of the upper arm and there is significant deflection at the edge of the claw. Shortening the upper arm to be about (*insert ratio here*) the size of the middle arm was done to fix the stress and deflection issues. It was eventually chosen that the upper arm should be  m long and the middle arm is 0.7 m long. 

To create the claw, the initial concept design was referenced. The concept was designed with a four-bar system that translates linear motion (of a hydraulic) to dual, perpendicular linear motion (of the grippers). The links were designed first with the pin holes in mind for connecting the claw pieces together. Secondary links were made to allow room for the arm upon which the claw is mounted. The gripper was initially designed with a flat face, but was subsequently changed mid-modeling to have a channel that can hold rubber or other adhesive for better grip when the claw is in use.

The hydraulic was designed based off 

### Explanation of Required Analyses

There were two analyses done, one in SOLIDWORKS and one in ANSYS. The analysis done in SOLIDWORKS was done on an assembly of the entire claw to identify what the critical angles of the claw are for analysis, the maximum deflection at the claw, and the critical areas of stress in the arm were. The analysis done in ANSYS was done on each of the critical parts individually to determine if they had a factor of safety of at least 3 for static stresses and at least 2 for fatigue stresses. The static factor of safety was tested by comparing the von Mises stress to the Yield Strength of 6061 aluminum. The fatigue factor of safety was tested by using a zero-based loading, the Goodman mean stress theory, a design life of 1 million cycles, and the von Mises stress.  

(*Insert SOLIDWORKS analysis here*) 

The teaching version of ANSYS that is installed on the GWC 481 lab computers was needed for the ANSYS analysis. The student version of ANSYS has a cap on the number of nodes and elements a model can use for its mesh. Every analysis in ANSYS exceeded this number of nodes and elements allowed in the student version, so the teaching version of ANSYS was required for every analysis. 

The parts chosen for an in-depth analysis in ANSYS were (*insert things here*). Each of these parts were analyzed using an initial mesh size of 5 mm. Their geometry with their initial mesh size can be seen in the images below: 

Claw Mesh: 

![image alt](https://github.com/jbruzas/Stress-and-Strain-Gang/blob/main/figures/claw_mesh.png)

There are many places on each part that require a very fine mesh to analyze. To make the analysis as efficient as possible, the faces that had the highest stress were selected to include in an automatic convergence analysis. Only these selected faces will be analyzed with the automatic convergence analysis instead of the entire structure. This saves a lot of time, nodes, and elements. The convergence analysis was chosen to have a maximum change in von Mises stress of 5%. The results of the ANSYS analysis to find the static factor of safety and the fatigue factor of safety can be seen in the table below: 

| Part Analyzed | Static Safety Factor | Fatigue Safety Factor |
| --------------| ------------ | ------- |
| Claw | 3.71 | 2.47 |

### Discussion of Design for Assembly 

### Updated Risks and/or Weaknesses Addressed
With the analysis, there are key locations where stress concentrations can cause the hydraulic arm to fail. With most of the arm's material being 6061-T6, the yield stress of the material is 276 MPa (~40,000 psi). With this in mind, the stress concentrations locate around the arm that connects to the claw. Due to the extruded cuts to allow the claw to maneuver freely without interference, the sharp corners are prone to larger von Mises stresses. To accommodate for these large values, fillets were added, but the concentrations still prevail.

Another weakness is the length ratio of the arm that connects to the base and the arm that connects to the claw. Initially, while the arm that connects to the base does not undergo large amounts of stress, the arm that connects to the claw does. With a maximum weight of 200 kg, if the length of the arm is too long, then it can snap due to the very large bending stress. Finding the ratio between the two arms is important, where the criteria is to ensure that the upper arm does not snap but can also still pick up objects properly. The final ratio chosen between the two arms is (*Insert ratio here*). Another way this issue was addressed was by making the upper arm taller than it was initally. Initally, the arm was constructed as a flat plate that was wider than it was tall, which ended up being a mistake. 

| Syntax    | Description |
| --------- | ----------- |
| Table     | Organizes data |
| Markdown  | Plain text formatting |
| Among | Us | 

https://huanuohyd.com/what-is-a-hydraulic-cylinder/
