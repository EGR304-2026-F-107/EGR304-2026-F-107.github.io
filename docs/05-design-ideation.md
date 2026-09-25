---
title: Design Ideation
---

## Intro/overview

The goal of this project is to develop a low-cost desktop robotic arm capable of performing precise and repeatable automated pick-and-place tasks. The system is intended to provide an accessible platform for engineering students, STEM educators, hobbyists, makers, and beginning robotics programmers to learn and experiment with robotics, embedded systems, programming, and automation.

The purpose of this design ideation process is to explore a wide range of possible features and design solutions that can satisfy the user needs and product requirements identified in the previous stages of the project. These ideas will be organized, evaluated, and combined into three distinct robotic arm design concepts.


## Generating Ideas


## Generating Ideas

To begin the ideation process, the team reviewed the user needs and product requirements developed during the previous stages of the project. The initial brainstorm focuses on generating multiple possible features that could satisfy the functional, mechanical, software, safety, usability, and modularity requirements of the desktop robotic arm.

At this stage, ideas were not eliminated based on cost, complexity, or feasibility. The purpose of the initial brainstorm was to generate a wide range of possible solutions that could later be sorted, ranked, and combined into different product concepts.

|                        requirement / need |             feature            | detail                                                                             |
| ----------------------------------------: | :----------------------------: | ---------------------------------------------------------------------------------------------- |
| PR-01: Programmed pick-and-place sequence | Pre-programmed motion sequence | Store a predefined series of joint movements for automatic pick-and-place operation.           |
| PR-01: Programmed pick-and-place sequence |     Waypoint-based movement    | Allow the arm to move through a series of programmed positions.                                |
| PR-01: Programmed pick-and-place sequence |    Record-and-playback mode    | Allow users to manually position the arm and save the positions for later playback.            |
| PR-01: Programmed pick-and-place sequence |      State-machine control     | Divide the pick-and-place task into states such as approach, grasp, move, release, and return. |
| PR-01: Programmed pick-and-place sequence |    Adjustable movement delay   | Allow timing between different stages of the sequence to be changed.                           |
| PR-01: Programmed pick-and-place sequence |      Repeating cycle mode      | Automatically repeat the programmed sequence for demonstrations or testing.                    |
|  PR-02: Repeatable programmed positioning |          Servo motors          | Provide controlled angular positioning at each robotic joint.                                  |
|  PR-02: Repeatable programmed positioning |         Stepper motors         | Provide repeatable incremental movement of the robotic joints.                                 |
|  PR-02: Repeatable programmed positioning |         Rotary encoders        | Measure actual joint position and provide position feedback.                                   |
|  PR-02: Repeatable programmed positioning |  Closed-loop position control  | Compare commanded and measured joint positions and correct positioning error.                  |
|  PR-02: Repeatable programmed positioning |      Mechanical hard stops     | Provide consistent physical limits for selected joint movements.                               |
|  PR-02: Repeatable programmed positioning |         Motion profiles        | Use controlled acceleration and deceleration to improve repeatability and reduce vibration.    |
|             PR-03: Secure object handling |   Two-finger parallel gripper  | Use two opposing fingers to grasp common demonstration objects.                                |
|             PR-03: Secure object handling |      Three-finger gripper      | Provide additional contact points for objects with irregular shapes.                           |
|             PR-03: Secure object handling |    Suction-cup end effector    | Pick up lightweight objects with smooth surfaces using vacuum suction.                         |
|             PR-03: Secure object handling |        Soft gripper pads       | Add compliant material to the gripper fingers to increase friction and reduce object damage.   |
|             PR-03: Secure object handling |    Adjustable gripper width    | Allow the gripper opening to accommodate objects of different sizes.                           |
|             PR-03: Secure object handling |     Force-sensitive gripper    | Measure gripping force to determine whether an object is held securely.                        |
|          PR-04: Stable repeated operation |       Rigid arm structure      | Use a mechanically rigid frame to reduce flex during repeated movement.                        |
|          PR-04: Stable repeated operation |       Low-backlash joints      | Reduce mechanical play between moving components.                                              |
|          PR-04: Stable repeated operation |   Smooth acceleration control  | Limit sudden motor acceleration that could cause vibration or instability.                     |
|          PR-04: Stable repeated operation |    Joint position monitoring   | Check joint positions during repeated operation to detect unexpected errors.                   |
|          PR-04: Stable repeated operation |     Automated cycle counter    | Record the number of completed pick-and-place cycles during testing.                           |
|          PR-04: Stable repeated operation |      Automatic fault stop      | Stop repeated operation when a motion or sensor error is detected.                             |
|              PR-05: Calibration procedure |    Automatic homing sequence   | Move each joint to a known reference position during startup.                                  |
|              PR-05: Calibration procedure |    Limit-switch calibration    | Use physical switches to establish reference joint positions.                                  |
|              PR-05: Calibration procedure |         Encoder zeroing        | Use encoder reference values to establish joint zero positions.                                |
|              PR-05: Calibration procedure |   Guided software calibration  | Guide the user through calibration using step-by-step instructions.                            |
|              PR-05: Calibration procedure |       Calibration button       | Provide a dedicated control to begin the calibration process.                                  |
|              PR-05: Calibration procedure |    Stored calibration values   | Save calibration parameters so they can be reused after restarting the system.                 |
|        PR-06: Consistent calibration |    Mechanical reference stops   | Provide fixed mechanical reference points to help joints return to the same starting position.     |
|        PR-06: Consistent calibration | Nonvolatile calibration storage | Store calibration parameters in memory so they remain available after power is removed.            |
|        PR-06: Consistent calibration |    Startup calibration check    | Check stored joint reference values when the robotic arm is powered on.                            |
|        PR-06: Consistent calibration |    Encoder-based verification   | Compare measured encoder positions with stored reference positions to verify calibration.          |
|        PR-06: Consistent calibration |   Calibration status indicator  | Use an LED or software indicator to show whether the robotic arm is properly calibrated.           |
|        PR-06: Consistent calibration | Automatic recalibration routine | Allow the system to repeat the homing or calibration sequence when an error is detected.           |
| PR-07: Programmable movement control |       Joint-angle commands      | Allow users to command specific angular positions for individual joints.                           |
| PR-07: Programmable movement control |   Cartesian position commands   | Allow users to specify desired end-effector positions using X, Y, and Z coordinates.               |
| PR-07: Programmable movement control |       PC control interface      | Allow movement commands to be entered and executed from a computer.                                |
| PR-07: Programmable movement control |     Serial command interface    | Allow movement commands to be transmitted through a serial communication connection.               |
| PR-07: Programmable movement control |    Adjustable movement speed    | Allow users to change the speed of programmed robotic movements.                                   |
| PR-07: Programmable movement control |  User-defined motion sequences  | Allow users to create and save custom sequences of robotic arm movements.                          |
|               PR-08: Gripper control |       Servo-driven gripper      | Use a servo motor to control gripper opening and closing.                                          |
|               PR-08: Gripper control |     Open and close commands     | Provide simple software commands for opening and closing the gripper.                              |
|               PR-08: Gripper control |    Variable gripper position    | Allow the user to specify different gripper opening widths.                                        |
|               PR-08: Gripper control |    Adjustable gripping force    | Allow gripping force to be modified for different objects.                                         |
|               PR-08: Gripper control |    Gripper position feedback    | Use a sensor or encoder to determine the current gripper position.                                 |
|               PR-08: Gripper control |     Automatic grasp command     | Allow a programmed sequence to activate the gripper automatically when the arm reaches the object. |
|      PR-09: Clear setup instructions |        Quick-start guide        | Provide a short step-by-step guide for first-time startup and operation.                           |
|      PR-09: Clear setup instructions |          Wiring diagram         | Provide a labeled diagram showing how motors, sensors, power, and the controller are connected.    |
|      PR-09: Clear setup instructions |      Assembly illustrations     | Use diagrams or images to show the correct mechanical assembly procedure.                          |
|      PR-09: Clear setup instructions |   Software installation guide   | Provide instructions for installing the required programming and control software.                 |
|      PR-09: Clear setup instructions |        Startup checklist        | Provide a checklist that users can follow before operating the robotic arm.                        |
|      PR-09: Clear setup instructions |    QR-code documentation link   | Provide a QR code that directs users to digital setup instructions and documentation.              |
|    PR-10: Modular hardware expansion |   Interchangeable end effector  | Allow different grippers or tools to be installed without redesigning the complete robotic arm.    |
|    PR-10: Modular hardware expansion |     Standard mounting holes     | Use standardized mounting locations so accessories can be added to the robotic arm.                |
|    PR-10: Modular hardware expansion |     Plug-and-play connectors    | Use removable electrical connectors to simplify replacement or addition of components.             |
|    PR-10: Modular hardware expansion |   Expandable controller ports   | Reserve available input/output ports for future sensors and accessories.                           |
|    PR-10: Modular hardware expansion |    Replaceable joint modules    | Design individual joint assemblies so they can be removed or upgraded independently.               |
|    PR-10: Modular hardware expansion | Modular controller architecture | Separate motor, sensor, and communication functions so individual modules can be upgraded later.   |
|              PR-11: Future sensor integration |      Available analog input ports     | Reserve analog input channels for sensors such as force, distance, or light sensors.                  |
|              PR-11: Future sensor integration |     Available digital input ports     | Reserve digital input pins for switches, encoders, and other digital sensors.                         |
|              PR-11: Future sensor integration |      I2C communication interface      | Provide an I2C connection for adding compatible digital sensors.                                      |
|              PR-11: Future sensor integration |      SPI communication interface      | Provide an SPI connection for higher-speed sensor communication.                                      |
|              PR-11: Future sensor integration |       Modular sensor connectors       | Use standardized connectors so sensors can be added or replaced easily.                               |
|              PR-11: Future sensor integration |   Expandable software sensor library  | Organize software so new sensor drivers can be added without rewriting the entire control system.     |
|                    PR-12: Stop robotic motion |         Emergency stop button         | Provide a physical emergency stop button that immediately stops robotic motion.                       |
|                    PR-12: Stop robotic motion |         Software stop command         | Provide a control interface command that stops the current movement sequence.                         |
|                    PR-12: Stop robotic motion |          Motor enable switch          | Allow motor power or motor-driver output to be disabled independently.                                |
|                    PR-12: Stop robotic motion |     Fault-triggered automatic stop    | Stop the robotic arm automatically when an abnormal operating condition is detected.                  |
|                    PR-12: Stop robotic motion |            Joint-limit stop           | Stop motion when a joint reaches its allowed movement limit.                                          |
|                    PR-12: Stop robotic motion |        Communication-loss stop        | Stop robotic motion if communication with the main controller or user interface is lost.              |
|                     PR-13: Physical stability |               Wide base               | Increase the base footprint to reduce tipping during arm movement.                                    |
|                     PR-13: Physical stability |             Weighted base             | Add mass to the base to improve stability during extended arm positions.                              |
|                     PR-13: Physical stability |              Rubber feet              | Add high-friction feet to reduce sliding on a desktop surface.                                        |
|                     PR-13: Physical stability |         Clamp mounting system         | Allow the robotic arm to be secured directly to a table or workbench.                                 |
|                     PR-13: Physical stability |      Low center-of-gravity design     | Position heavier components lower in the structure to improve stability.                              |
|                     PR-13: Physical stability |       Reinforced base structure       | Use a rigid base frame to reduce flex and movement during operation.                                  |
|            PR-14: Electrical operating limits |         Regulated power supply        | Provide stable voltage levels that remain within component operating specifications.                  |
|            PR-14: Electrical operating limits |         Overcurrent protection        | Use a fuse or electronic protection circuit to limit excessive current.                               |
|            PR-14: Electrical operating limits |           Voltage monitoring          | Measure supply voltage to detect conditions outside the allowed operating range.                      |
|            PR-14: Electrical operating limits |           Current monitoring          | Measure motor or system current to identify overload conditions.                                      |
|            PR-14: Electrical operating limits |  Separate motor and logic power rails | Separate motor power from controller power to reduce electrical disturbances and protect electronics. |
|            PR-14: Electrical operating limits |    Motor-driver protection features   | Use motor drivers with built-in thermal, overcurrent, or undervoltage protection.                     |
| PR-15: Accessible to beginning robotics users |    Simple graphical user interface    | Provide basic movement controls through an easy-to-understand graphical interface.                    |
| PR-15: Accessible to beginning robotics users |     Beginner programming examples     | Provide simple example programs for common robotic arm operations.                                    |
| PR-15: Accessible to beginning robotics users |       Preset demonstration mode       | Allow beginners to run a prepared pick-and-place demonstration without writing code.                  |
| PR-15: Accessible to beginning robotics users |    Labeled controls and connectors    | Clearly identify buttons, ports, motors, and other important system connections.                      |
| PR-15: Accessible to beginning robotics users |         Step-by-step tutorials        | Provide guided instructions that introduce users to basic robotic arm functions.                      |
| PR-15: Accessible to beginning robotics users | Error messages with suggested actions | Display understandable error information together with basic troubleshooting guidance.                |
| PR-16: Educational value through programmable operation |       Editable example programs       | Provide sample programs that users can modify to observe changes in robotic arm behavior.                                                  |
| PR-16: Educational value through programmable operation |    Joint-by-joint programming mode    | Allow users to command individual joints separately to understand robotic motion.                                                          |
| PR-16: Educational value through programmable operation |      Adjustable motion parameters     | Allow users to change speed, joint angle, timing, and sequence parameters for experimentation.                                             |
| PR-16: Educational value through programmable operation |       Sensor experiment support       | Allow users to add sensors and incorporate sensor data into programmed robotic actions.                                                    |
| PR-16: Educational value through programmable operation |          Motion visualization         | Display commanded joint positions or end-effector movement to help users understand the relationship between software and physical motion. |
| PR-16: Educational value through programmable operation |   Progressive programming exercises   | Provide activities that progress from basic manual movement to complete automated pick-and-place sequences.                                |
|                     PR-17: Remain within project budget |         Low-cost servo motors         | Use affordable motors that provide sufficient torque and positioning performance for the intended demonstrations.                          |
|                     PR-17: Remain within project budget |    Common off-the-shelf components    | Select widely available components to reduce cost and simplify replacement.                                                                |
|                     PR-17: Remain within project budget |      3D-printed structural parts      | Manufacture selected arm components using low-cost additive manufacturing.                                                                 |
|                     PR-17: Remain within project budget |     Single-controller architecture    | Use one main microcontroller when practical to reduce electronics cost.                                                                    |
|                     PR-17: Remain within project budget |           Standard fasteners          | Use common screws, nuts, and mounting hardware instead of specialized hardware.                                                            |
|                     PR-17: Remain within project budget |      Reusable modular components      | Design components so motors, sensors, and electronics can be reused during future upgrades instead of replacing the complete system.       |
|                PR-18: Clear troubleshooting information |         Troubleshooting guide         | Provide a list of common problems, possible causes, and recommended solutions.                                                             |
|                PR-18: Clear troubleshooting information |          Error-code reference         | Assign identifiable error codes or messages to common system faults.                                                                       |
|                PR-18: Clear troubleshooting information |            Diagnostic mode            | Provide a software mode that tests motors, sensors, gripper operation, and communication individually.                                     |
|                PR-18: Clear troubleshooting information |     Wiring troubleshooting diagram    | Provide a labeled connection diagram that users can reference when checking electrical problems.                                           |
|                PR-18: Clear troubleshooting information | Calibration troubleshooting procedure | Provide specific steps for diagnosing homing and calibration problems.                                                                     |
|                PR-18: Clear troubleshooting information |           FAQ documentation           | Provide answers to common setup, programming, calibration, and operating questions.                                                        |





## Step Three

Add your context and tables

## Step Four

Add your different product concepts stuff here

## Step Six (video link)
Embedded a YouTube video that covers the 
