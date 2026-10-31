---
title: Home
---
<center>
<font size="8">Simple Educational Robotic Arm<br>
<font size="5">Team 107<br>
**Submission: Oct 30, 2026**<br>
Fall 2026<br>
<font size="4">Arizona State University<br>
**EGR 304**<br>
<font size="4">Zane Reynolds<br>

</center>


## Project Summary

> Team 107 is building a **Simple Educational Robotic Arm**: a low-cost desktop arm that performs a repeatable pick-and-place sequence and is meant for students, educators and hobbyists who are learning robotics and embedded systems. The system is split into three boards, each built around its own PIC18F57Q43 Curiosity Nano and owned by one team member. The **Arm Motion Control** board drives the arm joint's 6 V gearmotor through a FAN8100N H-bridge and reports when the arm is in position. The **Gripper & Object Handling** board opens and closes a servo gripper and senses grip force with an FSR 402. The **User Controls & Safety** board reads the emergency stop, start/pause button and speed knob, and shows the system state with LEDs and a buzzer. The boards share eight signals over a daisy-chained 8-pin ribbon cable (SAFE_OK, RUN_REQ, GRIP_CMD, OBJ_HELD, ARM_IN_POS, SPEED_SET, GRIP_FORCE and GND), so each board can be built, tested and replaced on its own while the safety signal from the User board can stop all motion at any time.

## Team Introduction

We are Team 107. This website documents how the robotic arm was designed: the user needs and product requirements, the design ideation and concept selection, the team block diagram, the software proposal and the signal structure between the three boards. Each team member's individual datasheet covers the detailed design of their own board which including component selection, schematic, bill of materials and power budget.

## Team Members and Individual Datasheets

| **Team Member** | **Subsystem** | **Individual Datasheet** |
| --------------- | ------------- | ------------------------ |
| Yixiang Ren | Arm Motion Control | [Individual Datasheet](https://crackoxide.github.io/CrackOxide_EGR304_Fall26.github.io/) |
| Canyon Miller | Gripper & Object Handling | [Individual Datasheet](https://canyonmill60.github.io/EGR304DataSheetTemplate/) |
| Dunyue Yang | User Controls & Safety | [Individual Datasheet](https://idtrfmnhcw.github.io/idtrfmnhcw_EGR304_F26.github.io/) |

## Where to Find Things

| Section | What it contains |
|---|---|
| [Team Organization](02-Team-Organization.md) | Team charter, mission statement and team roles |
| [User Needs and Benchmarking](03-User-Needs-and%20Benchmarking.md) | Benchmarked products and the organized user needs |
| [Product Requirements](04-Product-Requirements.md) | Stakeholders, use cases and requirements PR-01 to PR-18 |
| [Design Ideation](05-design-ideation.md) | Brainstorm, ranked features, three concepts and how the final concept was chosen |
| [Team Block Diagram](06-team-block-diagram.md) | How the three boards, their parts and their power fit together |
| [Software Proposal](07-Software%20Proposal.md) | What each board's firmware does and how it meets the requirements |
| [Process Diagram](08-Process%20Diagram.md) | Flowchart of one pick-and-place cycle across the three boards |
| [Message Structure](09-Message%20Structure.md) | The eight ribbon signals, who drives them and the handshake between boards |
