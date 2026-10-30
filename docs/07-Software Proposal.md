---
title: Software Proposal
---

# Software Proposal

## Simple Educational Robotic Arm — Team 107

### Overview

The purpose of the software is to control the movement,
positioning, and gripping operations of the Simple
Educational Robotic Arm.

The robotic arm is divided into three subsystems,
with each subsystem responsible for a specific
part of the overall operation.

The system uses PIC18F57Q43 Curiosity Nano
microcontrollers to process inputs, control
outputs, and communicate between subsystems.

### Software Objectives

The proposed software will:

1. Initialize the microcontroller peripherals
   required for each subsystem.

2. Receive commands to control robotic arm
   movement and gripper operation.

3. Generate the required control signals for
   the robotic arm actuators.

4. Read the gripper's force-sensitive resistor
   through the analog-to-digital converter (ADC).

5. Use force sensor measurements to help
   prevent excessive gripping pressure.

6. Exchange commands and status information
   between subsystems through the planned
   communication interfaces.

7. Support safe operation by responding to
   stop commands and detected faults.

### Gripper Subsystem Operation

The Gripper & Object Handling subsystem uses
a Kitronik Klaw Mk2 robotic gripper and an
FSR 402 force sensor.

The PIC18F57Q43 will generate servo control
pulses to open and close the gripper.

The FSR 402 produces a variable electrical
signal that is conditioned by an MCP6004
operational amplifier and read through
the microcontroller's ADC.

The software will use these measurements to
monitor gripping force and adjust or stop
gripper movement when necessary.

### Implementation Status

This document describes the proposed software
architecture. Final pin assignments, peripheral
configuration, communication protocol, and
control thresholds will be verified during
implementation and testing.


[example link to idealab](https://idealab.asu.edu)


## Proposed Software Operating Sequence

The robotic arm software will use a repeated
control loop to receive commands, operate
the arm, monitor the gripper, and report status.

### Step 1: System Initialization

When the system starts, each PIC18F57Q43
microcontroller will initialize its required
peripherals, including GPIO, ADC, timers,
servo control outputs, and UART interfaces
where applicable.

The system will begin in a safe, inactive
state until valid commands are received.

### Step 2: Receive User Commands

The system will wait for commands requesting
arm movement, positioning, or gripper operation.

The responsible subsystem will interpret the
command and determine the required action.

### Step 3: Safety Check

Before commanding motion, the software will
check applicable safety conditions.

If a stop request or detected fault is active,
the software will prevent new motion commands.

### Step 4: Arm Movement

The arm-control subsystems will generate the
signals required to move the robotic arm
toward the requested position.

Movement details will depend on the final
actuator and controller configurations.

### Step 5: Gripper Operation

The Gripper & Object Handling subsystem will
receive an open or close command.

The PIC will generate the appropriate servo
control pulses for the Kitronik Klaw Mk2
gripper mechanism.

### Step 6: Force Sensor Measurement

The FSR 402 force sensor will measure contact
pressure at the gripper.

The sensor signal will pass through the
MCP6004 signal-conditioning circuit before
being measured by the PIC ADC.

### Step 7: Gripper Control

The software will compare the force sensor
reading against a calibrated threshold.

If the threshold is reached, the software
will stop commanding further closure or
adjust the gripper position as appropriate.

The final threshold and control behavior
will be determined through testing.

### Step 8: Status Communication

The subsystems will exchange relevant
commands and status information through
their planned communication interfaces.

The exact message format and timing will
be finalized during integration.

### Step 9: Repeat

After completing an operation, the system
will return to its command-processing loop
and wait for the next requested action.

## Software Development Status

This operating sequence represents the
proposed software behavior.

Peripheral configurations, communication
protocols, motion control methods, and
safety responses will require implementation
and verification before the system is
considered operational.


## Subsystem Communication and Software Responsibilities

### System Architecture

The Simple Educational Robotic Arm is divided
into three subsystems, each controlled by a
PIC18F57Q43 Curiosity Nano microcontroller.

Each subsystem is responsible for its own
sensors, actuators, and local control functions.

The subsystems will communicate to coordinate
arm movement, gripper operation, and system status.

### Subsystem 1: Arm Control

The arm-control software will:

1. Receive movement commands.
2. Determine the requested movement.
3. Generate control signals for its actuators.
4. Monitor applicable inputs and operating conditions.
5. Report operating status to the other subsystems.

### Subsystem 2: Arm Positioning

The positioning software will:

1. Receive positioning commands.
2. Control the assigned positioning actuators.
3. Monitor relevant feedback signals, if available.
4. Coordinate movement with the other subsystems.
5. Report completion or fault conditions.

### Subsystem 3: Gripper & Object Handling

The gripper software will:

1. Receive open and close commands.
2. Generate servo control pulses for the
   Kitronik Klaw Mk2 robotic gripper.
3. Read the FSR 402 force sensor using the ADC.
4. Monitor gripping force against a calibrated
   threshold.
5. Prevent additional closure when the force
   threshold is reached.
6. Report gripper status to the other subsystems.

### Communication Interface

The proposed communication system uses UART
connections between the microcontrollers.

Each subsystem will have designated transmit
and receive connections.

The current gripper schematic identifies:

- UART_TX: RB4
- UART_RX: RE2
- Common ground between connected boards

The final UART peripheral configuration and
pin assignments must be verified in MCC.

### Proposed Communication Messages

| Message | Purpose |
|---|---|
| MOVE | Request arm movement |
| POSITION | Request a positioning operation |
| GRIP_OPEN | Request gripper opening |
| GRIP_CLOSE | Request gripper closing |
| GRIP_STATUS | Report gripper state |
| STOP | Request motion to stop |
| ERROR | Report a detected fault |

These messages are proposed examples rather
than an implemented communication protocol.

The team will determine the final message
format, addressing method, baud rate, and
error-handling behavior during integration.

### Coordination and Safety

The subsystems will coordinate operations so
that movement and gripping commands are
processed in an appropriate sequence.

Each controller will check relevant safety
conditions before operating its actuators.

If a fault or stop condition occurs, the
affected subsystem will prevent further
commanded motion and report its status.

The final safety behavior will be validated
during system testing.

### Integration Status

The communication architecture is currently
proposed.

Successful UART communication, command
handling, subsystem coordination, and fault
responses remain to be implemented and tested.



## References


