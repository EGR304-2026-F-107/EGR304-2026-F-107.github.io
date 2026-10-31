---
title: Team Block Diagram
---

## Introduction
**This block diagram shows how our team's three boards work together in a pick-and-place robotic arm system. Each board uses a Microchip PIC18F57Q43 Curiosity Nano and handles one function: Arm Motion Control drives a 6 V gearmotor through a FAN8100N H-bridge; Gripper & Object Handling drives the Kitronik Klaw Mk2 servo and reads an FSR 402 force sensor; User Controls & Safety reads the E-stop, start/pause button and speed knob and drives the status LEDs and buzzer.**

**The boards are connected in a daisy chain with 8-pin ribbon cables. Pins 1–5 carry digital signals (SAFE_OK, RUN_REQ, GRIP_CMD, OBJ_HELD, ARM_IN_POS), pins 6–7 carry analog signals (SPEED_SET, GRIP_FORCE), and pin 8 is GND. Every sensor and actuator connects only to its own board's microcontroller, so only high-level status and command signals cross between boards. Arrows show signal direction.**

**Power is drawn the same way on every board: supply wiring is shown only from each source (9 V wall adapter or the PC's USB port) to its regulators, and the rail each block runs from is written in bold inside the block instead of drawing a supply line to it. Every Curiosity Nano runs at its factory 3.3 V from USB, so all ribbon signals are 0 / 3.3 V, and all grounds are common through ribbon pin 8.**

## Research Question

* With only have 8-pin connectors. How to divide functionality across the team in a way that minimizes interconnections between teammates?
* Does the system layout ensure each teammate meets minimum project requirements?
* What are the risks to the current system if lose a teammate? How to de-risk the system design by grouping and/or distributing similar functions between teammates?

## Images
![Team 107 block diagram](image/Team107_Team_Block_Diagram.png)
**Figure 1:** Team block diagram (click the image to enlarge).

## Results
1. **Interconnections are kept to a minimum.** The system is divided by physical ownership. Every sensor and actuator is wired only to the microcontroller on its own board, so no raw sensor or motor signal crosses a ribbon cable. Only high-level status and command signals are shared between boards: five digital, two analog and ground. This fits the whole team on one 8-pin connector, with one wire per signal.<br>
2. **Every teammate meets the minimum project requirements.** Each board has its own microcontroller, at least one ribbon connector, and at least one sensor or actuator, and each board uses different peripherals:
    * The Arm board has a DC gearmotor, an H-bridge and two PWM outputs.
    * The Gripper board has a servo (PWM) and a force sensor (ADC).
    * The User board has an E-stop, buttons, a speed knob (ADC), a DAC output for SPEED_SET, LEDs and a buzzer.<br>
3. **Losing a teammate's board is a known risk.**
    * If the User board is missing, SAFE_OK is never driven, so the system stays safely stopped and cannot run.
    * If the Gripper board is missing, the chain between the other two boards breaks, because it sits in the middle.
    * If the Arm board is missing, there is no motion.

   We reduce these risks in four ways:<br>
  (1) Every board's digital inputs have pull-down resistors and every board has test points or headers, so jumpers can simulate a missing teammate's signals and the other boards can still be tested.<br>
  (2) The Gripper board passes pins 1–8 straight through from Connector 1 to Connector 2, so a single cable can run directly from the Arm board to the User board and the chain still works without the Gripper board.<br>
  (3) All three boards use the same MCU, the same pin map and the same signal definitions, so any teammate can write a stub for another board's interface.<br>
  (4) Safety does not depend on firmware messages. SAFE_OK is a dedicated wire from the User board's E-stop logic, and the pull-downs on the receiving boards turn a broken or unplugged cable into "stop".<br>

## Design Decision-Making Process

**Why three boards split by function.** The arm was divided into Arm Motion Control, Gripper & Object Handling, and User Controls & Safety, so that each member owns one physical function end to end and each board can be built and tested alone. Grouping all user inputs and status outputs on one board puts the safety logic in a single place. Keeping the motor on its own board keeps motor current and noise away from the other boards.

**Why an 8-pin parallel ribbon instead of a serial bus.** Each signal has its own wire and exactly one driver, so the link needs no protocol firmware. It can be checked with a multimeter or an LED, and a fault on one wire does not corrupt the others. The two analog signals (SPEED_SET and GRIP_FORCE) are sent as voltages from a DAC, which avoids encoding numbers. Every Curiosity Nano runs at 3.3 V, so all ribbon signals use the same 0 / 3.3 V levels.

**Why a daisy chain (Arm – Gripper – User).** The Gripper sits in the middle because it exchanges signals with both other boards, and it passes the ribbon through 1:1 so the Arm and User boards still see every signal.

**Why each board has its own power.** Each board has its own 9 V adapter input and regulators for its actuator: the 6 V motor rail on the Arm board, the 5 V servo rail on the Gripper board and the 5 V buzzer rail on the User board. Every Nano is powered from USB. This way each board can be powered and tested alone, and motor current never flows through a teammate's board. Grounds are joined through ribbon pin 8.

### How the block diagram meets the product requirements

| Requirement | How the architecture meets it |
|---|---|
| PR-01 Pick-and-place sequence | The ARM_IN_POS → GRIP_CMD → OBJ_HELD handshake sequences the arm and gripper across boards |
| PR-02 / PR-04 Repeatable, stable motion | The Arm board drives its joint from a regulated 6 V rail with PWM speed control, independent of the other boards' loads |
| PR-03 / PR-08 Gripper control | The Gripper board's servo and FSR 402 close the grip on command and report OBJ_HELD and GRIP_FORCE |
| PR-07 / PR-16 Programmable movement | Speed (SPEED_SET) and the sequence are set in firmware and by the speed knob, and the result is visible on the arm |
| PR-10 / PR-11 Modular, expandable | Independent boards, keyed connectors, pass-through wiring and spare-I/O headers |
| PR-12 Stop motion | The E-stop on the User board drives SAFE_OK low, and every board stops when SAFE_OK is 0, including when the cable is unplugged |
| PR-14 Electrical limits | Each board has its own fused supply and regulators sized in its power budget; all logic levels are 3.3 V |
| PR-15 Beginner accessibility | Each board does one job, and signals can be watched with an LED or a meter |

## Conclusions and Future Work

The block diagram fixes the hardware architecture, the parts on each board, the power arrangement and the 8-pin interface for Team 107.

Future work includes:

* building the three boards and testing the ribbon signals between them;
* verifying the SAFE_OK stop behavior with the cable connected and with it unplugged;
* adding joint position feedback on the Arm board's expansion header if testing shows that timed moves are not repeatable enough.

The block diagram will be updated after integration testing and instructor feedback.

## Resources

The block diagram source files (editable draw.io file and exported PNG) are available as a [*Zip download*](image/Team107_Team_Block_Diagram_source.zip). The draw.io file can also be opened directly: [*Team107_Team_Block_Diagram.drawio*](image/Team107_Team_Block_Diagram.drawio).



