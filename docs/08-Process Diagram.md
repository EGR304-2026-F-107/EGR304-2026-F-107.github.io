---
title: Process Diagram
---

## Introduction
** **

## Research Question



## Process Diagram
<img width="3082" height="879" alt="EGR304_Team107_Blockdiagram drawio" src="https://github.com/user-attachments/assets/c51c77c4-6b99-4f84-99cd-0f502bdfddd8" />
**Figure 1:** Process Diagram <br>
## External Link

[Link to the block diagram](https://github.com/EGR304-2026-F-107/EGR304-2026-F-107.github.io/blob/main/EGR304_Team107_Blockdiagram.drawio)

## Results
1. We divided the system by physical ownership. Every sensor and actuator is wired only to the microcontroller on its own board, so no raw sensor or motor signal ever crosses a ribbon cable. Only high-level status and command signals are shared between boards. This keeps the whole team within 7 usable pins.<br>
2. Yes. Each board has its own microcontroller, at least one ribbon connector, and at least one sensor or actuator: the Arm board has a motor and a position sensor, the Gripper board has a servo plus object and force sensors, and the User board has an E-stop, buttons, a speed knob, LEDs and a buzzer. The three roles are unique. Together they use different peripherals.<br>
3. Losing the User board means SAFE_OK is never driven, so the system stays safely stopped and cannot run. Losing the Gripper board breaks the chain between the other two boards, because it sits in the middle. Losing the Arm board removes all motion. We reduce these risks in four ways:<br>
  (1).Every connector has a test header, so jumpers can simulate a missing teammate's signals and the other boards can still be tested.<br>
  (2). We use a cable that can run directly from the Arm board to the User board, so the chain survives without the Gripper board.<br>
  (3). All three boards use the same MCU, the same pin map and a shared handshake module, so any teammate can write a stub for another board's interface.<br>
  (4). The Arm board gets a local stop input that is ANDed with SAFE_OK in hardware, so safety does not depend on a single board.<br>
