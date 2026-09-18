---
title: Product Requirements
---

## Project Objective
Our project aims to develop a low-cost, modular desktop robotic arm capable of performing precise and repeatable automated pick-and-place tasks. The system is intended to demonstrate how repetitive tasks can be automated while remaining accessible to engineering students, STEM educators, hobbyists, makers, and beginning robotics programmers.

The product requirements were developed from the user needs identified during the Voice of the Customer benchmarking process. Existing products such as the Elephant Robotics myCobot 280, Yahboom DOFBOT, DOBOT Magician, Hiwonder xArm 1S, and Adeept 5-DOF Robotic Arm Kit were examined to identify desirable features and common problems.
The primary objectives of the product are to:

1.Provide precise and repeatable robotic movement.
2.Reliably grasp, move, and release objects.
2.Maintain a low overall system cost.
3.Make assembly and calibration straightforward.
4.Provide simple and understandable programming and control.
5.Use modular hardware and software that can be expanded.
6.Provide clear documentation and troubleshooting information.
7.Provide an educational platform for learning robotics and embedded systems.
8.Operate safely in a classroom, laboratory, or desktop environment.
9.Provide a stable physical platform for repeated pick-and-place operations.

The final design should balance performance, affordability, accessibility, and educational value rather than focusing exclusively on maximum industrial performance.

## Stakeholders

 **Target group**
**Engineering Students**

Students are expected to be one of the primary users of the robotic arm. The system should allow students to learn about robotics, embedded systems, programming, sensors, motors, control systems, and automation through hands-on experimentation.

**STEM Educators**

Teachers and instructors may use the robotic arm as a classroom demonstration or laboratory platform. The system should therefore be easy to set up, demonstrate, and explain.

**Hobbyists and Makers**

Hobbyists should be able to use the robotic arm for experimentation, custom programming, and small automation projects without requiring expensive industrial equipment.
Beginning Robotics Programmers

The system should provide a relatively low learning curve so that users with limited robotics experience can begin programming and operating the arm.

**Small-Scale Automation Users**

The system should demonstrate basic automation concepts such as repetitive movement, object sorting, and pick-and-place operations.

**Secondary Stakeholders**

**Project Team**

The engineering team is responsible for designing, assembling, programming, testing, and documenting the product.

**Future Designers and Developers**

Because the system is intended to be modular, future users should be able to modify or expand the hardware and software without redesigning the entire system.
**Manufacturers and Suppliers**

Manufacturing stakeholders need components that are affordable, available, compatible, and practical to assemble.

## Use Cases

### Use Case #1: Engineering Student Performing Pick-and-Place

An engineering student uses the robotic arm in a laboratory to learn about automated pick-and-place operations.

The student places several small objects within the designated workspace and starts the robotic arm. The arm moves to a predefined position, activates the gripper, picks up an object, moves to another predefined position, releases the object, and returns to its starting position.

The student then modifies the program to change the object's starting or ending position.
**User Requirements**

The system should:

Complete the pick-and-place sequence consistently.
Position the gripper accurately enough to grasp the intended object.
Repeat the sequence multiple times without requiring manual recalibration.
Allow the user to modify movement parameters.
Provide understandable programming examples.
Allow the student to observe the relationship between software commands and physical movement.
Provide a safe method of stopping the arm if unexpected movement occurs.
**Verification**

This use case can be verified through a repeated pick-and-place test. The arm will be commanded to perform the same operation multiple times and the success rate, positioning error, and calibration stability will be recorded.

### Use Case #2: STEM Educator Demonstrating Robotic Automation
A STEM educator uses the robotic arm during a classroom demonstration.

The educator demonstrates how a repetitive manual task can be automated by programming the arm to move objects between two locations.

Students observe the movement and then modify the program to change the movement sequence.

**User Requirements**

The system should:

.Be simple enough to demonstrate without extensive setup.
.Provide clear startup instructions.
.Provide clear programming examples.
.Allow students to modify the robotic sequence.
.Operate safely around users.
.Provide visible or understandable feedback about the system's operating state.
.Be sufficiently reliable to complete a classroom demonstration without repeated troubleshooting.
**Verification**
The educator setup procedure will be timed and documented. The system will also be tested through repeated demonstrations to determine whether the arm can complete the programmed task consistently.

## Design Aspects

1. **Hardware / Product Design**
   The robotic arm should use a compact desktop form factor suitable for a laboratory, classroom, or workbench.

The mechanical design should prioritize:

*Stable operation.
*Repeatable joint movement.
*Reliable object handling.
*Accessible components.
*Modular construction.
*Easy maintenance.
*Low vibration.
*Compact size.
*Affordable components.
The arm should include an end effector capable of securely gripping the intended demonstration objects.

The mechanical structure should be sufficiently rigid that repeated movement does not cause excessive movement or instability.
**Hardware Requirements**
*The base shall remain stable during normal operation.
*The joints shall provide controlled movement.
*The gripper shall securely hold the intended test objects.
*Components should be replaceable individually when practical.
*Wiring should be organized and protected from moving components.
*The system should provide an accessible emergency stop or software-controlled stop mechanism.
  
2. **Software / Functionality**
     The software should provide simple control of the robotic arm while allowing advanced users to modify the system.

The system should support:

*Manual movement.
*Programmed movement.
*Pick-and-place sequences.
*Position control.
*Gripper control.
*Calibration.
*Basic error handling.
*Future sensor integration.
*Future computer-vision integration.

The software should use a modular structure so that additional functions can be added without completely rewriting the control system.
**Software Requirements**
The software will:

*Allow the user to command individual robotic movements.
*Allow the user to execute a programmed sequence.
*Allow the user to control the gripper.
*Provide a method for calibration.
*Provide clear instructions for starting the system.
*Provide understandable examples for beginning programmers.
*Allow future sensors or accessories to be integrated.

3. **Interactivity & User Experience**
   The robotic arm should provide an approachable user experience for users with limited robotics experience.

The user interface should prioritize:

*Simple controls.
*Clear feedback.
*Understandable error messages.
*Straightforward calibration.
*Accessible documentation.
*Minimal unnecessary setup.

The system should allow a beginner to progress from basic manual movement to programmed automation.
The user should not need extensive robotics knowledge to perform the basic pick-and-place demonstration.
4. **Customization**
The system should be designed so that users can modify or expand the robotic arm.

Potential customization should include:

*Different end effectors.
*Additional sensors.
*Computer vision.
*Alternative control interfaces.
*Different programmed movement sequences.
*Additional objects or sorting tasks.
*Software modifications.
*Future robotic arm improvements.

The modular design should allow components to be replaced or upgraded without requiring replacement of the complete system.
5. **Manufacturing**

The product should use commonly available components where practical to reduce cost and simplify replacement.

Manufacturing considerations include:

*Low component cost.
*Availability of replacement components.
*Repeatable assembly.
*Accessible fasteners and connectors.
*Organized wiring.
*Modular components.
*Minimal specialized manufacturing equipment.

Assembly instructions should be clear enough that a user with basic technical skills can construct or service the system.
6. **Safety**

The robotic arm should be designed to operate safely in classroom, laboratory, and desktop environments where users may be in close to motor and moving components.

Safety considerations include:

*The system should provide an accessible emergency stop or software-controlled stop mechanism.
*The robotic arm should avoid unexpected motion during startup and calibration.
*Wiring and electrical connections should be secured and protected from moving joints.
*Moving joints and the gripper should be arranged to reduce the risk of pinch points and accidental contact.
*The robotic arm should remain physically stable during normal operation.
*Electrical components should operate within their specified voltage and current limits.

The final design should ensure safe operation while maintaining the accessibility and educational value of the system.

## Requirement Criteria Specifications

| ID | Requirement | Verification Method | Target |
|---|---|---|---|
| PR-01 | The robotic arm shall perform a programmed pick-and-place sequence. | Demonstration | Complete the sequence successfully at least 9 out of 10 attempts. |
| PR-02 | The arm shall repeatedly move to programmed positions. | Test | At least 90% of repeated movements shall fall within the project's defined positioning tolerance. |
| PR-03 | The gripper shall securely hold the intended test object. | Test | Successfully hold and move the designated object through the complete test sequence. |
| PR-04 | The system shall maintain stable operation during repeated movement. | Test | Complete at least 20 consecutive pick-and-place cycles without requiring manual repositioning. |
| PR-05 | The system shall provide a calibration procedure. | Demonstration | A new user shall be able to complete calibration using the provided instructions. |
| PR-06 | Calibration shall remain sufficiently consistent for repeated demonstrations. | Test | Complete the defined pick-and-place test without recalibration during the test sequence. |
| PR-07 | The system shall provide programmable movement control. | Demonstration | User can modify at least one programmed movement and observe the corresponding physical change. |
| PR-08 | The system shall provide gripper control. | Demonstration | User can command the gripper to open and close through the control software. |
| PR-09 | The system shall provide clear setup instructions. | Inspection/Demonstration | A first-time user can follow the instructions to start the system successfully. |
| PR-10 | The system shall support modular hardware expansion. | Inspection | At least one component can be replaced or added without redesigning the entire system. |
| PR-11 | The system shall support future sensor integration. | Inspection/Analysis | Controller and software architecture shall provide an available interface for additional sensors. |
| PR-12 | The system shall provide a method of stopping robotic motion. | Demonstration | User can stop the arm during operation without disconnecting the complete system. |
| PR-13 | The robotic arm shall remain physically stable during normal operation. | Test | Base shall not move outside the defined operating area during the repeated-motion test. |
| PR-14 | The system shall use components within their specified electrical operating limits. | Analysis/Test | Measured voltage and current shall remain within component specifications. |
| PR-15 | The system shall be accessible to beginning robotics users. | User Test | A beginner can complete the basic startup and demonstration procedure using the provided documentation. |
| PR-16 | The system shall provide educational value through programmable operation. | Demonstration | User can modify a programmed sequence and successfully execute the modified sequence. |
| PR-17 | The system shall remain within the team's defined project budget. | Analysis | Total project cost shall remain below the team's established budget limit. |
| PR-18 | The system shall provide clear troubleshooting information. | Inspection/User Test | Documentation shall include solutions for the most common setup, calibration, and programming problems. |
# Requirement Traceability

| User Need Category | Related Product Requirements |
|---|---|
| Accuracy & Repeatability | PR-01, PR-02, PR-04 |
| Gripper & Object Handling | PR-03 |
| Programming & Control | PR-07, PR-08 |
| Documentation & Troubleshooting | PR-05, PR-09, PR-18 |
| Education & User Experience | PR-15, PR-16 |
| Sensors, Vision & Expansion | PR-10, PR-11 |
| Calibration, Maintenance & Repair | PR-05, PR-06, PR-10 |
| Assembly, Wiring & Components | PR-10, PR-14 |
| Power, Stability & Physical Design | PR-13, PR-14 |
| Safety | PR-12, PR-14 |
| Cost & Accessibility | PR-15, PR-17 |

## Open Questions

1.) What is the maximum object weight that the robotic arm needs to pick up?
2.) What object dimensions should the gripper accommodate?
3.) What positioning accuracy is required for successful pick-and-place operation?
4.) How many degrees of freedom are required for the intended demonstrations?
5.) Which microcontroller or processor will be used for the final design?
6.) Which motors and motor drivers provide the appropriate combination of cost, torque, and positioning accuracy?
7.) What sensors should be included in the initial design?
8.) Should computer vision be included in the initial prototype or reserved for future expansion?
9.) What programming language or development environment should be used?
10.) What control interface will provide the best balance between simplicity and flexibility?
11.) What is the maximum acceptable total project cost?
12.) What safety mechanism should be used as the emergency stop?
13.) How much calibration should be required after powering on the system?
14.) What testing procedure will be used to define and measure repeatability?
15.) What manufacturing or fabrication method will be used for the arm structure?
16.) Which components should be designed to be replaceable?
17.) What documentation is necessary for a beginning robotics student to successfully assemble and program the system?
18.) What future sensors, end effectors, or software features should the modular architecture support?
